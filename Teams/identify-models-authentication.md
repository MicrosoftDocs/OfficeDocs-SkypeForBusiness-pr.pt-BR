---
title: Modelos de identidade e autenticação para Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Saiba mais sobre os diferentes modelos de identidade para Microsoft Teams como somente nuvem e híbrido. Conheça também a autenticação multifator.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c12e7242241c8c6d7ac03bc3c66804198acd746e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836059"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modelos de identidade e autenticação para Microsoft Teams

Microsoft Teams dá suporte a todos os modelos de identidade disponíveis com Microsoft 365 e Office 365, que incluem:

- **Somente na** nuvem: as contas de usuário são criadas e gerenciadas em Microsoft 365 ou Office 365 e armazenadas no Azure Active Directory (Azure AD). As credenciais de login do usuário (nome da conta e senha) são validadas pelo Azure AD.

- **Híbrida**: as contas de usuário geralmente são gerenciadas em uma floresta local dos Serviços de Domínio do Active Directory (AD DS). Dependendo da configuração, a validação de credenciais pode ser feita pelo Azure AD, pelo AD DS ou por um provedor de identidade federado. Este modelo usa a sincronização de diretório do AD DS para o Azure AD com o Azure AD Conexão.

Para obter mais informações, [consulte Microsoft 365 identidade e Azure AD](/microsoft-365/enterprise/about-microsoft-365-identity).

## <a name="configurations"></a>Configurações

Dependendo das decisões da sua organização sobre qual modelo de identidade e configuração você usa, as etapas de implementação podem variar.

Se você ainda não tiver implantado Microsoft 365 ou Office 365 um modelo de identidade, use esta tabela. 

|Modelo de identidade |Lista de verificação da implantação  |Informações adicionais  |
|---------|---------|---------|
|Tudo     |<ol type="1"><li>Compare Microsoft 365 e Office 365 plano e obtenha uma assinatura e um locatário.</li><li>Crie uma Microsoft 365 ou Office 365 para seu locatário.</li><li>Comprar Microsoft 365 ou Office 365 para o locatário</li><li>Configurar domínios e contas de usuário de administrador.</li></ol>  |<ul><li>[Office 365 de plano](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Comparar Microsoft 365 planos de negócios](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Comprar ou remover licenças de assinatura](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Adicionar licenças a uma inscrição](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurar o Microsoft 365 para empresas](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Adicionar um domínio com o assistente de instalação](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[O Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) está disponível para ajudá-lo.  |
|Identidade de nuvem     |<ul><li>Criar contas de usuário com o Centro de administração do Microsoft 365</li></ul> |<ul><li>[Adicionar usuários e atribuir licenças](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identidade híbrida     |<ol type="1"><li>Instale o Azure AD Conexão.</li><li>Configurar a sincronização de diretórios.</li><li>Gerenciar usuários e grupos com ferramentas do AD DS.</li></ol> |<ul><li>[Configurar a sincronização de diretórios](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identidade híbrida com autenticação federada    |<ol type="1"><li>Instale e configure um provedor de identidade federado, como o AD FS.</li><li>Instale o Azure AD Conexão e configure a sincronização de diretórios e a autenticação federada.</li><li>Gerenciar usuários e grupos com ferramentas do AD DS.</li></ol> |<ul><li>[Planejar sua implantação do AD FS](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[Lista de verificação: Implantar seu farm de servidor de federação](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[Configurar acesso à extranet para o AD FS](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[Definir uma confiança entre o AD FS e o Azure AD](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[Verificar e gerenciar registro único com o ADFS](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[Configurar a sincronização de diretórios](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Autenticação multifator

As senhas são o método mais comum de autenticação para entrar em um computador ou serviço online, mas também são as mais vulneráveis. As pessoas podem escolher senhas fáceis e usar as mesmas senhas para várias logins em computadores e serviços diferentes. 

Para fornecer um nível adicional de segurança para entrar, use a autenticação multifato (MFA), que exige uma senha e um método de verificação adicional, como:

- Uma mensagem de texto enviada para um telefone que exige que o usuário digite um código de verificação.
- Uma chamada telefônica.
- O Microsoft Authenticator de telefone inteligente.
- Outros métodos disponíveis com identidade híbrida e autenticação federada.

O MFA é suportado com qualquer plano Microsoft 365 ou Office 365 que inclui Microsoft Teams. É altamente recomendável que, no mínimo, você exige MFA para essas contas que são [atribuídas](/microsoft-365/admin/add-users/about-admin-roles)a funções de administrador , como Teams administrador de serviço.

Você também deve lançar o MFA para seus usuários. Depois que os usuários estão inscritos no MFA, na próxima vez que eles entrarem, eles verão uma mensagem solicitando que eles configurarem seu método de verificação adicional. 

Para obter mais informações, consulte [Autenticação multifa factor para Microsoft 365](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).