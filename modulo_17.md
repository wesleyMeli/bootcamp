## Exercicio 01

---

- **Como seria o fluxo de execução a partir do momento em que
recebemos um request?**

   - Criar um metodo schedule, que em um determinado intervalo de tempo irá executar uma chamada para obter os dados de conversão de [N] moedas, e salvar/atualizar 
em um banco de dados KVS de cach.
   - Na camada de service, executar uma chamada para o metodo na camada api.service, responsavel por obter os dados de um item a partir do item_id.
   - De volta na camada de service, executar uma nova chamada para o metodo na camada api.service, responsavel por obter os dados de conversao de uma respectiva moeda
de um banco de dados de cach, KVS.   
   - Na camada de servico, executar a função para conversão do valor da moeda.
  
- **O que aconteceria se recebêssemos 1000 pedidos por minuto? E se
recebermos 100.000? Esta API tem uma implementação correta? Que
perguntas vocês fariam para pensar em otimizações a serem feitas à
API?**

    - Qual o tempo de resposta dá API.
    - Qual a margem de erro das cotações.

- **Assumindo que as citações mudam uma vez por dia, que opção
podemos tomar para melhorar esta API?**

    - Programar a schedule para executar a cada 24 hrs.
    - Criar um sistema de mensageria para atualizar as cotações a cada 24 hrs ou quando uma cotação for atualizada.
    
