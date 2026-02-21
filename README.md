let
  createUser = rec {
    user = {
      name = "Samad Olaibi";
      role = "Software Engineer";
      languages = [ "Yoruba" "English" ];
      programmingLanguages = [ "Java" "Python" "Typescript" ];
      infrastructure = [ "Nix" "Ansible" "Docker" "Terraform" ];
    };
    
    userInfo = ''
      Name: ${user.name}
      Role: ${user.role}
      Spoken Languages: ${builtins.concatStringsSep ", " user.languages}
      Programming Languages: ${builtins.concatStringsSep ", " user.programmingLanguages}
      Infrastructure: ${builtins.concatStringsSep ", " user.infrastructure}
    '';
  };
in
  builtins.trace createUser.userInfo createUser
