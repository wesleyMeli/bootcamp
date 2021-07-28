## Toolkits e Microservicios
---
### Exercício 1
	
- **A referida api tem o seguinte SLA de resposta**   
  - Tempo de resposta   
  - Média: 40 ms    
  -	P95: 150 ms   
  -	P99: 300 ms   
  -	MAX: 400 ms   
  -	Taxa de erro: 0,9%    

**Elabore uma proposta para os valores de configuração do restclient e explique por que cada valor:**   
  - **Timeout:** 150 ms   
  -	**Retries**   
    -	**Quantidade:** 3   
    -	**Estratégia:** Simple Strategy   

### Exercício 2

 - **Inferir por que isso acontece e propor uma alteração na política de repetição e no código de status que nosso microsserviço retorna.**
		
   -  O tempo de espera para uma nova solicitação é muito curto em relação ao tempo solicitado pela api consumida. 
      - **Solução:**     
        - Alterar o corpo da resposta com a request 429 para informar o tempo necessário para uma nova solicitação.   
        - Aumentar o tempo de espera para uma nova tentativa com.    
        - Usar um time randômico antes de uma nova tentativa.    
        - “Travar” a requisição e aguardar o tempo estimado para uma nova tentativa.     
        - Usar dados em cache, no servidor que iremos acessar para evitar um request 429, ou um cache no nosso servidor para evitar efetuar uma nova requisição.    
