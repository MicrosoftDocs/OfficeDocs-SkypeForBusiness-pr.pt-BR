---
title: "Modelos de identidade e autenticação no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba sobre os diferentes modelos de identidade no Microsoft Teams, como Nuvem, Sincronizada e Federada. Conheça também a autenticação multifator."
ms.openlocfilehash: b3976a23bc4e165b5a21c99c57356428d0e6767b
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2017
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Modelos de identidade e autenticação no Microsoft Teams
==========================================

O Microsoft Teams suporta todos os modelos de identidade que estão disponíveis no Office 365. Os modelos de identidade suportados incluem:

-   **Identidade em Nuvem**: Neste modelo, um usuário é criado e gerenciado no Office 365, armazenado no Azure Active Directory e a senha é verificada pelo Azure Active Directory.

-   **Identidade Sincronizada**: Neste modelo, a identidade do usuário é gerenciada em um servidor local e as contas e os hashes de senha são sincronizados com a nuvem. O usuário insere no local a mesma senha que na nuvem e, ao iniciar sessão, a senha é verificada pelo Azure Active Directory. Este modelo usa a ferramenta Microsoft Azure Active Directory Connect.

-   **Identidade Federada**: Este modelo exige que uma identidade sincronizada com a senha do usuário seja verificada pelo provedor de identidade no local. Com esse modelo, o hash de senha não precisa ser sincronizado com o Azure AD, e o Active Directory Federation Services (ADFS) ou um provedor de identidade terceiro é usado para autenticar usuários no diretório ativo local.

<a name="configurations"></a>Configurações
--------------

Dependendo das decisões da sua organização de qual modelo de identidade implementar e utilizar, os requisitos de implementação podem variar. Consulte a tabela de requisitos abaixo para garantir que sua implantação atenda a esses pré-requisitos. Se você já tiver implantado o Office 365 e já tiver implementado o método de identidade e autenticação, ignore estas etapas.


|Modelo de identidade |Lista de verificação da implantação  |Informações adicionais  |
|---------|---------|---------|
|Tudo     |<ol type="1"><li>Comparar as opções de plano do Office 365 a obter uma inscrição</li><li>Criar um locatário do Office 365</li><li>Atribuir licenças do Office 365 ao locatário</li><li>Configurar domínios e usuários administradores</li><li>Continuar as instruções específicas do modelo de identidade</li></ol>          |<ul style="list-style-type:none"><li>[Opções de plano do Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparar os planos do Office 365 Business](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Comprar licenças para a sua inscrição do Office 365 for Business](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Adicionar licenças a uma inscrição](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar o Office 365 for Business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Adicionar usuários e domínios com o assistente de configuração](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Nota: Se precisar de assistência, [a equipe do Microsoft FastTrack for Office 365](https://go.microsoft.com/fwlink/?linkid=854618) está disponível para ajudar.</li></ul>          |
|Identidade em Nuvem     |<ol type="1"><li>Criar usuários usando o portal de administração do Office 365</li></ol>           |<ul style="list-style-type:none"><li>[Adicionar usuários no Office 365 individualmente ou em massa](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Identidade Sincronizada     |<ol type="1"><li>Instalar o Azure AD Connect</li><li>Configurar a sincronização de diretório</li><li>Crie usuários usando ferramentas de gerenciamento do diretório ativo no local</li></ol>         |<ul style="list-style-type:none"><li>[Configurar a sincronização de diretório para o Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Nota: Os hashes de senha devem ser sincronizados para o Office 365 fazer a autenticação.</li></ul>         |
|Identidade Federada    |<ol type="1"><li>Instalar o Azure AD Connect</li><li>Configurar a sincronização de diretório</li><li>Instalar e configurar um Provedor de Identidade Federada (recomendação: ADFS)</li><li>Crie usuários usando ferramentas de gerenciamento do diretório ativo no local</li></ol>           |<ul style="list-style-type:none"><li>[Configurar a sincronização de diretório para o Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planejar sua implantação do AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Lista de verificação: Implantar seu farm de servidor de federação](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurar acesso à extranet para o AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Definir uma confiança entre o AD FS e o Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificar e gerenciar registro único com o ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Lista de compatibilidade da federação do Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Nota: Os hashes de senha não precisam ser sincronizados ao Azure Active Directory.</li></ul>         |

Consulte os guias [Escolha de um modelo de registro para o Office 365](https://go.microsoft.com/fwlink/?linkid=854626) e [Entender a identidade do Office 365 e o Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) para obter mais detalhes.

<a name="multi-factor-authentication"></a>Autenticação multifator 
----------------------------

Os planos do Office 365 suportam a autenticação multifator (MFA) que aumenta a segurança dos logins de usuários nos serviços do Office 365. Com a MFA para o Office 365, os usuários devem confirmar pois uma chamada telefônica, uma mensagem de texto ou uma notificação de aplicativo no seu smartphone após inserir corretamente sua senha. O usuário poderá iniciar sessão somente depois que esse segundo fator de autenticação for satisfeito.

A autenticação multifator é suportada em qualquer plano do Office 365 que inclua o Microsoft Teams. Os planos de inscrição do Office 365 que incluem o Microsoft Teams são discutidos posteriormente abaixo na seção de Licença.

Depois de os usuários estarem inscritos na MFA, na próxima vez que um usuário entrar, ele verá uma mensagem solicitando que configure seu segundo fator de autenticação. Os métodos de autenticação suportados são:


|Tipo de locatário  |Opções de segundo fator de MFA disponíveis  |Notas  |
|---------|---------|---------|
|**Somente na nuvem**     |MFA para Office 365 <ul><li>Chamada telefônica</li><li>Mensagem de texto</li><li>Notificação no aplicativo móvel</li><li>Código de verificação no aplicativo móvel</li></ul>        |[Plano de autenticação multifator para implantações do Office 365](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**Configuração híbrida (modelo de identidade sincronizada ou federada)**     |<ul><li>MFA para Office 365</li><li>Módulo Azure MFA (integrado com ADFS)</li><li>Cartão inteligente físico ou virtual (integrado com ADFS)</li></ul>         |Nota: Estão disponíveis soluções adicionais de MFA com [Provedores de identidade compatíveis com a federação do Azure AD](http://go.microsoft.com/fwlink/p/?LinkId=510953)         |
