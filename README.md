### Accceder con la terminal git bash
```
cd .ssh
ssh-keygen -t rsa -b 2048 -C "curso_github"
```
- asignar un nombre:
id_rsa_curso_github
- enter enter
### Mostrar el contenido del archivo pub
```
cat id_rsa_curso_github.pub
```
### github
- (copiar el contenido id_rsa_curso_github.pub)
- Acceder a github
- en el perfil (settings)
- click en SSH and GPG Keys
- Click en new ssh key
- asignamos un titulo (id_key_curso_github)
- Pegar el contenido del archivo .pub

### Verificamos
```
ssh -T git@github.com
git@github.com: Permission denied (publickey).
```
### Carga tu clave en el agente ssh
```
eval "$(ssh-agent -s)"
``` 
- Ahora añade tu clave
```
ssh-add ~/.ssh/id_rsa_curso_github
```
- finalmente volver a probar
```
ssh -T git@github.com
```