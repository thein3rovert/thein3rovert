```nix
let
  createUser = {
    user = {
      name = "Samad Olaibi";
      role = "Software Engineer";
      languages = [ "Yoruba" "English" ];
    };
    
    userInfo = ''
      Name: ${user.name}
      Role: ${user.role}
      Spoken Languages: ${builtins.concatStringsSep ", " user.languages}
    '';
  };
in
  builtins.trace createUser.userInfo createUser
```
  
