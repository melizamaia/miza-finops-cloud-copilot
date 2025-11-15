📘 Guia de Criação do Ambiente no Azure AI Foundry

Este passo a passo demonstra como criar o ambiente necessário para desenvolver o agente MIZA – FinOps Cloud Copilot dentro do Azure AI Foundry, atendendo aos requisitos do desafio.

---

🧭 1. Acessando o Portal Azure

Acesse:

🔗 https://portal.azure.com/

No menu inicial, selecione Recursos.

![img-001](docs/img/img-001.png.png)

📌 Região recomendada: Canadá Oeste (melhor latência para o Brasil nas assinaturas AFG).

---

🗂 2. Criando o Grupo de Recursos

Abra o menu sanduíche (≡) e procure Resource Groups.

![img-002](docs/img/img-002.png.png)

Clique em Create para criar um novo grupo.

➕ Criar Grupo de Recursos

![img-003](docs/img/img-003.png.png)

🏷 Criar Tags (boa prática)

Adicione tags para organização e governança.

![img-004](docs/img/img-004.png.png)


✔ Revisar e Criar

![img-005](docs/img/img-005.png.png)

---

📦 3. Conferindo o Grupo de Recursos

Entre no grupo criado:

![img-006](docs/img/img-006.png.png)


Verifique se tudo foi criado corretamente:

![img-007](docs/img/img-007.png.png)

---

🛒 4. Criando o Serviço do Azure AI Foundry

No grupo de recursos, clique em Create e depois em Marketplace.

![img-008](docs/img/img-008.png.png)

No campo de busca, digite:

➡ "AI Foundry"

![img-009](docs/img/img-009.png.png)

---

🔍 5. Conferindo Providers

No Marketplace, verifique se todos os providers são Microsoft.

Se aparecer “Partner” → não está incluso no plano AFG.

Use a tabela da documentação oficial para checar os acrônimos.

![img-010](docs/img/img-010.png.png)

🟣 AFG = Azure Frontier Girls
Seu crédito da trilha é aplicado nesse provedor.

---

⚙ 6. Configuração da Criação

Tipo de Plano: Criar um recurso da Fábrica de IA no Azure

![img-011](docs/img/img-011.png.png)

Disponibilidade: marque All (os demais exigem configurações adicionais).

![img-012](docs/img/img-012.png.png)

Identidade atribuída automaticamente

![img-013](docs/img/img-013.png.png)


🔐 Encriptação

Mantenha Padrão.

![img-014](docs/img/img-014.png.png)

🏷 Adicione a Tag AFG

Importante para controle e governança da assinatura.

![img-015](docs/img/img-015.png.png)


✔ Validar e Criar

![img-016](docs/img/img-16.png.png)

---

🚀 7. Deployment

Após alguns segundos/minutos, o recurso será implantado.

![img-017](docs/img/img-017.png.png)

Clique em Ir para o recurso.

---

📡 8. Acessar o Azure AI Foundry Portal

No recurso criado, abra a aba Overview (Visão Geral).

![img-018](docs/img/img-018.png.png)


Clique em:

➡ Go to Azure AI Foundry Portal

![img-019](docs/img/img-019.png.png)

O portal abrirá em nova janela:

![img-020](docs/img/img-020.png.png)

---

🧱 9. Entendendo o Azure AI Foundry

O portal funciona como um frontend administrativo:
cada item da barra lateral chama um endpoint do back-end (API).

---

🤖 10. Acessando Modelos (Models)

![img-022](docs/img/img-022.png.png)

Aqui você encontra:

Modelos de linguagem (GPT, Phi, Mistral)

Modelos de visão

Modelos de fala

Modelos especializados

![img-023](docs/img/img-023.png.png)

---

🧩 11. Gerenciamento de Projetos

Você pode criar múltiplos projetos dentro do mesmo workspace.

![img-024](docs/img/img-024.png.png)

---

📁 12. Acessando Seu Projeto

![img-025](docs/img/img-025.png.png)


Entre no projeto ou clique novamente em:

➡ Go to Azure AI Foundry Portal

![img-026](docs/img/img-026.png.png)

---

📚 13. Portal já inicializado com bibliotecas

Lembrando que o ambiente já vem com bibliotecas pré-configuradas:

![img-027](docs/img/img-027.png.png)

🎉 Conclusão

Você configurou com sucesso:

✔ Grupo de Recursos
✔ Serviço Azure AI Foundry
✔ Tags de governança
✔ Ambiente operacional
✔ Acesso ao workspace e modelos