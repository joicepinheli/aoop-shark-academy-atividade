# 📱 Social Media Management App (ServiceNow)

**Desenvolvedora:** Joice Magda  
**Plataforma:** ServiceNow (PDI)  
**Status:** ✅ Concluído

## 📄 Sobre o Projeto
Este projeto consiste em uma aplicação Scoped desenvolvida na plataforma ServiceNow para centralizar e automatizar a gestão de postagens em mídias sociais corporativas. A solução abrange desde a estruturação do banco de dados até a experiência do usuário final no Portal.

O desenvolvimento foi dividido em 4 atividades principais, focando em **Data Modeling**, **Process Automation**, **Service Catalog** e **Employee Center**.

---

## 🚀 Funcionalidades Principais

### 1. Estrutura de Dados e UX (Back-end)
* Criação de Scoped Application dedicada.
* **Tabela Channel:** Gerenciamento de canais (LinkedIn, Instagram, etc) com contadores automáticos de posts.
* **Tabela Post:** Estendida da tabela *Task*, com campos de auditoria, data de publicação e métricas de engajamento (Cliques).
* **Menu de Navegação:** Módulos organizados hierarquicamente para facilitar o acesso dos gestores.

### 2. Automação Inteligente (Flow Designer)
Fluxo automatizado (`Social Media Post Flow`) que gerencia o ciclo de vida do post:
* ⏳ **Wait for Condition:** Aguarda a data de publicação agendada.
* 🔢 **Lógica Matemática:** Incrementa automaticamente o contador de posts no cadastro do Canal (+1) ao publicar.
* ⚡ **Lógica Condicional:** Monitora o engajamento. Se `Cliques < 500`, dispara notificações automáticas para o grupo de Gestores.
* 🔄 **Encerramento:** Finaliza o registro automaticamente após o período de follow-up.

### 3. Catálogo de Serviços (Front-end)
* **Record Producer:** Formulário amigável ("New Social Media Post") para solicitação de novas postagens.
* **Mapeamento de Variáveis:** Integração direta entre os inputs do usuário e a tabela de destino.
* **Segurança:** Utilização de *User Criteria* para restringir o acesso apenas aos grupos "Gestores" e "Analistas".

### 4. Portal do Colaborador (Employee Center)
* Integração nativa com o **Employee Center**.
* Configuração de **Menu Item** estratégico dentro do menu "More", permitindo acesso rápido à criação de posts sem necessidade da interface clássica.

---

## ✅ Checklist de Validação Técnica

Abaixo estão os critérios utilizados para validar a entrega e o funcionamento da aplicação.

### Atividade 1: Aplicação e Tabelas
- [ ] **Escopo:** Aplicação criada como "Social Media Management".
- [ ] **Tabela Channel:** Campos (Name, Followers, Url) e *Auto Number* configurados.
- [ ] **Tabela Post:** Estendida de *Task*, com campo *Total of Clicks* (Integer) e *Channel* (Reference).
- [ ] **Navegação:** Menu "Social Media Management" criado com módulos e separadores corretos.

### Atividade 2: Automação (Flow Designer)
- [ ] **Trigger:** O fluxo inicia na criação (`Created`) do registro de Post.
- [ ] **Permissões:** Execução configurada como *System User*.
- [ ] **Contador:** O campo *Number of Posts* do Canal soma +1 corretamente após a publicação.
- [ ] **Decisão (If):** O fluxo identifica corretamente se os cliques são `< 500`.
- [ ] **Ação:** E-mail é enviado para o grupo "Gestores" em caso de baixo engajamento.
- [ ] **Fim:** O estado do post muda para *Closed* ao final do processo.

### Atividade 3: Service Catalog
- [ ] **Item:** Record Producer "New Social Media Post" criado.
- [ ] **Variáveis:** Título, Canal e Conteúdo mapeados para a tabela.
- [ ] **UX:** Imagem de cabeçalho configurada.
- [ ] **Segurança:** *User Criteria* aplicado (Visível apenas para Gestores/Analistas).

### Atividade 4: Portal (Employee Center)
- [ ] **Menu Item:** Registro criado na tabela `sp_rectangle_menu_item`.
- [ ] **Hierarquia:** Item posicionado como filho ("Parent") do menu **More**.
- [ ] **Funcionamento:** O link abre corretamente o formulário dentro do portal `/esc`.

---

## 🛠️ Tecnologias Utilizadas
* **ServiceNow App Engine**
* **Flow Designer** (Low-code automation)
* **Service Portal / Employee Center**
* **User Criteria / ACLs**

---
*Projeto desenvolvido para fins educacionais e de portfólio.*
