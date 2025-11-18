📘 Guia de Criação do Ambiente no Azure AI Foundry

Seu copiloto para análise financeira e otimização de custos na nuvem Azure.

Este guia apresenta, de forma clara e prática, a criação do MIZA – FinOps Cloud Copilot dentro do Azure AI Foundry. Ele ajuda a equipe a entender melhor como a nuvem funciona, como organizar recursos e como montar um agente que conversa, interpreta comandos e aciona automações de FinOps para simular alertas de custo.

---

🧭 1. Acessando o Portal Azure

Acesse:

🔗 https://portal.azure.com/

No menu inicial, selecione Recursos.

![img-001](docs/img/img-001.png)

📌 Região recomendada: Canadá Oeste (melhor latência para o Brasil nas assinaturas AFG).

---

🗂 2. Criando o Grupo de Recursos

Abra o menu sanduíche (≡) e procure Resource Groups.

![img-002](docs/img/img-002.png)

Clique em Create para criar um novo grupo.

➕ Criar Grupo de Recursos

![img-003](docs/img/img-003.png)

🏷 Criar Tags (boa prática)

Adicione tags para organização e governança.

![img-004](docs/img/img-004.png)


✔ Revisar e Criar

---

📦 3. Conferindo o Grupo de Recursos

Entre no grupo criado:

![img-006](docs/img/img-006.png)


Verifique se tudo foi criado corretamente:

![img-007](docs/img/img-007.png)

---

🛒 4. Criando o Serviço do Azure AI Foundry

No grupo de recursos, clique em Create e depois em Marketplace.

![img-008](docs/img/img-008.png)

No campo de busca, digite:

➡ "AI Foundry"

![img-009](docs/img/img-009.png)

---

🔍 5. Conferindo Providers

No Marketplace, verifique se todos os providers são Microsoft.

Se aparecer “Partner” → não está incluso no plano AFG.

Use a tabela da documentação oficial para checar os acrônimos.

![img-010](docs/img/img-010.png)

🟣 AFG = Azure Frontier Girls
Seu crédito da trilha é aplicado nesse provedor.

---

⚙ 6. Configuração da Criação

Tipo de Plano: Criar um recurso da Fábrica de IA no Azure

![img-011](docs/img/img-011.png)

Disponibilidade: marque All (os demais exigem configurações adicionais).

![img-012](docs/img/img-012.png)

Identidade: deixe como **atribuição automática**.

![img-013](docs/img/img-013.png)

🔐 Encriptação

Mantenha a opção **Padrão**.

![img-014](docs/img/img-014.png)

🏷 Adicione a Tag AFG

Importante para controle e governança da assinatura.

![img-015](docs/img/img-015.png)


✔ Validar e Criar

![img-016](docs/img/img-016.png)

---

🚀 7. Deployment

Após alguns segundos/minutos, o recurso será implantado.

![img-017](docs/img/img-017.png)

Clique em Ir para o recurso.

---

📡 8. Acessar o Azure AI Foundry Portal

No recurso criado, abra a aba Overview (Visão Geral).

![img-018](docs/img/img-018.png)

Clique em:

➡ Go to Azure AI Foundry Portal

![img-019](docs/img/img-019.png)

O portal abrirá em nova janela:

![img-020](docs/img/img-020.png)

---

🧱 9. Entendendo o Azure AI Foundry

O portal funciona como um frontend administrativo:
cada item da barra lateral chama um endpoint do back-end (API).

---

🤖 10. Acessando Modelos (Models)

![img-022](docs/img/img-022.png)

Aqui você encontra:

- Modelos de linguagem (GPT, Phi, Mistral)  
- Modelos de visão  
- Modelos de fala  
- Modelos especializados

![img-023](docs/img/img-023.png)

---

🧩 11. Gerenciamento de Projetos

Você pode criar múltiplos projetos dentro do mesmo workspace.

![img-024](docs/img/img-024.png)

---

📁 12. Acessando Seu Projeto

![img-025](docs/img/img-025.png)


Entre no projeto ou clique novamente em:

➡ Go to Azure AI Foundry Portal

![img-026](docs/img/img-026.png)

---

📚 13. Portal já inicializado com bibliotecas

Lembrando que o ambiente já vem com bibliotecas pré-configuradas:

![img-027](docs/img/img-027.png)

---

📘 14. Criação do Agente no Azure AI Foundry

Para criar um novo agente, clique em **Create Agent**:

![img-028](docs/img/img-028.png)

Escolha o modelo GPT-4 Mini por ser leve, rápido e suficiente para nossa lógica financeira.

![img-029](docs/img/img-029.png)

Após selecionar o modelo, clique em Confirmar.

🔹 Adicionar instruções internas do agente

No catálogo de modelos, escolhemos o GPT-4 Mini para construir o chatbox.

No campo de instruções, insira o texto completo do comportamento do MIZA – FinOps Cloud Copilot.

![img-030](docs/img/img-030.png)

🔹 Adicionar descrição do agente

Preencha a descrição pública do agente:

![img-031](docs/img/img-031.png)

---

⚙️ 15. Criando Ações (Actions) para o Agente

As ações permitem que o agente execute tarefas externas — como registrar alertas financeiros via Logic App.

🔹 Abrir o menu de ações

No lado direito da tela, clique em Add Action.

![img-032](docs/img/img-032.png)

🔹 Criar Aplicativo Lógico (Logic App)

Selecione Gerar Aplicativo Lógico do Azure.

![img-033](docs/img/img-033.png)

Escolha a opção:

📌 Call external HTTP or HTTPS endpoints

![img-034](docs/img/img-034.png)

🔹 Criar e descrever a ação

Adicione:

Nome da ação

Descrição

Endpoint

Configurações da chamada HTTP

![img-035](docs/img/img-035.png)

🔹 Configurar parâmetros da requisição

Use:

HTTP Method: POST

Motivação: o agente enviará dados JSON para o endpoint do Logic App que registra alertas financeiros.

![img-036](docs/img/img-036.png)

🔹 Confirmar criação da ação

Clique em Confirm Resource.

![img-037](docs/img/img-037.png)

🔹 Criar o esquema do JSON

Defina o esquema (campos aceitos pelo alerta) e ajuste o que considerar necessário.

![img-038](docs/img/img-038.png)

🔹 Verificar se a ação foi criada

A ação deve aparecer na barra lateral direita como ativa.

![img-039](docs/img/img-039.png)

---

🧪 16. Testando o Agente no Playground

Abra o botão Playground no canto superior direito.

![img-040](docs/img/img-040.png)

Agora podemos testar o comportamento real do agente.

---

⚗️ 17. Prompt de Teste

🟪 **Teste — Alerta percentual**

Crie um alerta se meu custo de nuvem aumentar mais de 20% em relação ao mês passado.
Enviar para meliza@example.com.


O agente deve:

- Interpretar a condição  
- Confirmar com você  
- Chamar a ferramenta (ação do Logic App)  
- Retornar algo como:  
  **“Pronto! O alerta foi enviado.”**

Exemplos:

![img-041](docs/img/img-041.png)

![img-042](docs/img/img-042.png)

![img-043](docs/img/img-043.png)

📌 Recomendações Importantes

- Não pressione ENTER no meio da frase → isso pode quebrar o JSON da ação.  
- Escreva prompts completos em uma única linha, depois envie.

---

🧰 18. Tecnologias Utilizadas

O projeto MIZA – FinOps Cloud Copilot utiliza uma combinação de serviços e ferramentas da plataforma Azure para criar um agente inteligente com capacidade de automação via Logic Apps.

💠 Azure AI Foundry

Plataforma central onde o agente foi criado, configurado e testado.
Permite:

- Criar agentes com modelos de IA  
- Definir instruções internas  
- Adicionar actions  

🤖 Modelos de Linguagem (GPT-4 Mini)

Modelo leve e eficiente para:

Interpretar linguagem natural

Executar lógica do agente

Controlar chamadas para Logic Apps

Responder com clareza e rapidez

🔧 Azure Logic Apps

Usado para:

Criar endpoints HTTP

Receber dados gerados pelo agente

Simular o registro/envio de alertas financeiros

Automatizar fluxos acionados pelo Chat Copilot

🗂 Azure Resource Groups

Estrutura utilizada para organizar:

O workspace do Foundry

Logic Apps

Definições de tags e governança

Recursos relacionados ao projeto

🌐 Azure Portal

Interface administrativa usada para:

Criar e visualizar recursos

Validar deploys

Gerenciar permissões e configurações

📚 Bibliotecas Internas do Foundry

O ambiente já vem com:

SDKs para modelos

Ferramentas de teste

Suporte a JSON schemas

Ambientes pré-carregados para agentes

---

📖 19. Referências da Documentação Oficial do Azure

Essas referências foram utilizadas para guiar a criação, definição de ações e entendimento da arquitetura do Azure AI Foundry e Logic Apps.

🔗 Azure AI Foundry – Documentação Oficial

https://learn.microsoft.com/azure/ai-foundry/

🤖 Criar e Configurar Agentes (AI Agents Service)

https://learn.microsoft.com/azure/ai-foundry/concepts/agents

🔌 Actions e Integração com Logic Apps

https://learn.microsoft.com/azure/ai-foundry/how-to/agents-add-actions

https://learn.microsoft.com/azure/logic-apps/logic-apps-overview

🗂 Gerenciamento de Recursos no Azure

https://learn.microsoft.com/azure/azure-resource-manager/management/overview

⚙️ Modelos: GPT, Phi, Mistral e Outros

https://learn.microsoft.com/azure/ai-services/model-catalog/

🔐 Governança, Identidade e Controle de Acesso (IAM)

https://learn.microsoft.com/azure/role-based-access-control/overview