# kubernets
POC -  kubernets localhost


![image](https://user-images.githubusercontent.com/65586669/166185928-81f32338-b5d4-45af-b384-17d3d282659a.png)


# Objetivo

- Criar um cluster 
- Realizar pull da imagem criada utilizando o spring boot com os seguintes recursos:
  > http://localhost:8080/linguagens     : Retorna todas as linguagens utilizadas no projeto ficticio.

  ```
    [
      "JAVA",
      "JAVA_SCRIPT",
      "GO",
      "C_CHARP"
    ]
  ```

  > POST: http://localhost:8080/desenvolvedores  : Insere um registro a lista de desenvolvedores onde espera receber qual a linguagem o desenvolver utiliza no projeto:
  Example: body : 
  ```
    {
    "id":2020,
    "nome":"MAXWELL",
    "cargo":"Desenvolvedor",
    "linguagemPrincipal":"JAVA_SCRIPT"
    }
  ```
  
   > GET: http://localhost:8080/desenvolvedores  : Obtem todos os desenvolvedores registrados .

# Execução das etapas informadas:

- kube create cluster --name IC-DEV

- kubectl create deployment app --image=maxwellalvespe/app:latest

- kubectl expose deployment app --type=LoadBalancer --8080

- kubectl port-forward 'Nome_Servico' service/app 'porta' 8080

# Referencias:

> https://pt.wikipedia.org/wiki/Redirecionamento_de_portas<br/>
> https://kind.sigs.k8s.io/docs/user/quick-start/<br/>
> https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#create
