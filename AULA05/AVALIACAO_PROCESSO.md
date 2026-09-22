# Avaliação de Viabilidade de RPA - Lab 05

* **Cenário:** Cenário A
* **Nome do Processo:** Conciliação Bancária Diária
* **É viável para RPA?:** Sim

---

### Justificativa de Viabilidade

* **Repetitividade:** Processo diário, padronizado e executado sempre da mesma forma.
* **Regras de Negócio:** Regras fixas e claras. A validação depende apenas de cruzar o CNPJ e o valor exato.
* **Tipo de Dados:** Dados estruturados. O arquivo `.csv` permite a leitura direta das informações.
* **Volume:** Trabalho manual diário e repetitivo, ideal para automação e prevenção de erros humanos.

**Nota sobre o Cenário B:** O Cenário B é inviável para RPA tradicional porque decisões baseadas em "análise emocional" exigem julgamento humano e não possuem regras objetivas.

---

### Mapeamento Passo a Passo das Ações do Robô

1. Fazer login no portal do banco.
2. Baixar o arquivo do extrato diário em `.csv`.
3. Ler e organizar os dados do arquivo `.csv`.
4. Fazer login no sistema ERP.
5. Para cada lançamento do extrato:
   - Buscar a transação no ERP usando o **CNPJ** e o **Valor**.
   - **Se encontrar:** Realizar a baixa no ERP.
   - **Se não encontrar:** Gravar no log de exceções para verificação manual.
6. Gerar um relatório final com o resumo das baixas e divergências.
7. Enviar o relatório por e-mail para a equipe financeira.