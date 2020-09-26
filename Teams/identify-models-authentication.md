---
title: Modelos de identidade e autenticação do Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Saiba mais sobre os diferentes modelos de identidade do Microsoft Teams, como somente em nuvem e híbrido. Conheça também a autenticação multifator.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277111"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modelos de identidade e autenticação do Microsoft Teams

O Microsoft Teams dá suporte a todos os modelos de identidade disponíveis com o Microsoft 365 e o Office 365, que incluem:

- **Somente em nuvem**: as contas de usuário são criadas e gerenciadas no Microsoft 365 ou no Office 365 e armazenadas no Azure Active Directory (Azure AD). As credenciais de entrada do usuário (nome da conta e senha) são validadas pelo Azure AD.

- **Híbrido**: as contas de usuário são normalmente gerenciadas em uma floresta de serviços de domínio Active Directory (AD DS) local. Dependendo da configuração, a validação de credenciais pode ser feita pelo Azure AD, pelo AD DS ou por um provedor de identidade federada. Esse modelo usa a sincronização de diretório do AD DS para o Azure AD com o Azure AD Connect.

Para obter mais informações, consulte [modelos de identidade do Microsoft 365 e o Azure ad](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity).

## <a name="configurations"></a>Configurações

Dependendo das decisões da sua organização de qual modelo de identidade e configuração você usa, as etapas de implementação podem variar.

Se você ainda não implantou o Microsoft 365 ou o Office 365 e um modelo de identidade, use essa tabela. 

|Modelo de identidade |Lista de verificação da implantação  |Informações adicionais  |
|---------|---------|---------|
|Tudo     |<ol type="1"><li>Comparar as opções de plano do Microsoft 365 e do Office 365 e obter uma assinatura e um locatário.</li><li>Crie uma organização do Microsoft 365 ou do Office 365 para o seu locatário.</li><li>Comprar licenças do Microsoft 365 ou do Office 365 para o locatário</li><li>Configurar domínios e contas de usuário de administrador.</li></ol>  |<ul><li>[Opções de plano do Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparar planos do Microsoft 365 para empresas](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Comprar ou remover licenças de assinatura](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Adicionar licenças a uma inscrição](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar o Microsoft 365 para empresas](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Adicionar um domínio com o assistente de configuração](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[O Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) está disponível para ajudá-lo.  |
|Identidade de nuvem     |<ul><li>Criar contas de usuário com o centro de administração do Microsoft 365</li></ul> |<ul style="list-style-type:none"><li>[Adicionar usuários e atribuir licenças](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identidade híbrida     |<ol type="1"><li>Instale o Azure AD Connect.</li><li>Configurar a sincronização de diretório.</li><li>Gerenciar usuários e grupos com ferramentas do AD DS.</li></ol> |<ul style="list-style-type:none"><li>[Configurar a sincronização de diretório](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identidade híbrida com autenticação federada    |<ol type="1"><li>Instalar e configurar um provedor de identidade federada, como o AD FS.</li><li>Instalar o Azure AD Connect e configurar a sincronização de diretório e autenticação federada.</li><li>Gerenciar usuários e grupos com ferramentas do AD DS.</li></ol> |<ul><li>[Planejar sua implantação do AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Lista de verificação: Implantar seu farm de servidor de federação](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configurar acesso à extranet para o AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Definir uma confiança entre o AD FS e o Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Verificar e gerenciar registro único com o ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Configurar a sincronização de diretório](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Autenticação multifator

Senhas são o método mais comum de autenticação para entrar em um computador ou serviço online, mas elas também são mais vulneráveis. As pessoas podem escolher senhas fáceis e usar as mesmas senhas para várias entradas em diferentes computadores e serviços. 

Para fornecer um nível adicional de segurança para entradas, use a MFA (autenticação multifator), que exige uma senha e um método de verificação adicional, como:

- Uma mensagem de texto enviada para um telefone que exige que o usuário digite um código de verificação.
- Uma chamada telefônica.
- Aplicativo para telefone inteligente do Microsoft Authenticator.
- Outros métodos disponíveis com identidade híbrida e autenticação federada.

A MFA tem suporte em qualquer plano do Microsoft 365 ou do Office 365 que inclua o Microsoft Teams. É altamente recomendável que, pelo menos, você exija MFA para as contas às quais as [funções de administrador são atribuídas](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide), como o administrador do teams Service.

Você também deve implementar a MFA em seus usuários. Depois que os usuários estiverem registrados para a MFA, na próxima vez que entrarem, eles verão uma mensagem que pede para a configuração do método de verificação adicional. 

Para obter mais informações, consulte [autenticação multifator para o Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
