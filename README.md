# dio-lab-azure-apim
Projeto prático de configuração de segurança em APIs com Azure API Management. Implementação de Subscription Keys e validação avançada de JWT com OAuth 2.0 (Azure AD).

# 🛡️ Gerenciamento e Segurança de APIs com Azure API Management

Este repositório documenta a implementação prática de um Gateway de API seguro utilizando o **Azure API Management**. O projeto demonstra o domínio sobre políticas de segurança, controle de acesso e integração com provedores de identidade (Azure AD).

## 🚀 Tecnologias Utilizadas
* **Azure API Management (APIM):** Configuração de Gateway, Backends e Políticas.
* **Microsoft Entra ID (Azure AD):** Gestão de identidade e emissão de tokens.
* **OAuth 2.0 & JWT:** Protocolos de autenticação e autorização moderna.
* **Postman:** Testes de requisição e validação de segurança.

## 📋 Cenário Implementado

O objetivo foi proteger uma API de backend ("Echo API") garantindo que apenas clientes autenticados e autorizados pudessem acessá-la. A segurança foi aplicada em camadas:

1.  **Nível 1 - Subscription Key:** Acesso restrito a desenvolvedores com chaves de assinatura válidas (`x-api-key`).
2.  **Nível 2 - Validação JWT (OAuth 2.0):** Implementação de política `validate-jwt` para verificar:
    * Assinatura do token (Issuer).
    * Público alvo (Audience).
    * Validade temporal (Expiration).

## 📸 Evidências do Projeto

### 1. Configuração da Política de Segurança (JWT)
Configuração no Azure definindo os emissores e audiências permitidas.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0a1d5d82-d457-4ac4-96dc-08976e4ec00c" />


### 2. Teste de Segurança: Acesso Negado (401)
Demonstração da política bloqueando requisições com tokens inválidos ou escopos incorretos.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9a66fba4-af36-407a-b614-8676d3ef1759" />


### 3. Teste de Sucesso: Acesso Permitido (200 OK)
Validação final com Token Bearer correto (gerado via Client Credentials Flow) e Subscription Key.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1c66667f-937b-4b95-9e0b-60a044c16dfd" />


---

## 🛠️ Como Reproduzir

Para replicar este laboratório:
1.  Crie um serviço **API Management** no Azure.
2.  Importe a API de demonstração (Echo API).
3.  No **Azure AD**, registre uma aplicação e gere o `Client ID` e `Secret`.
4.  Configure a política `inbound` no APIM com o bloco `<validate-jwt>`.
5.  Teste o fluxo de credenciais via Postman.

## 📝 Conclusão
Este projeto solidificou conhecimentos em governança de APIs e arquitetura de segurança em nuvem, essenciais para o desenvolvimento de microsserviços modernos.

---
