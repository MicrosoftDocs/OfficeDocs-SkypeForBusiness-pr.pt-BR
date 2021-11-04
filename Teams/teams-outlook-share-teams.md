---
title: Compartilhar com Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre o recurso Compartilhar Teams, que permite que os usuários compartilhem emails e anexos de email de Outlook para qualquer chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd8e31f83927c459f4a188f7316d000c13e5ef91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774261"
---
# <a name="share-to-teams-from-outlook"></a>Compartilhar para Teams de Outlook

O compartilhamento Teams do Outlook (Compartilhar para Teams) permite que os usuários compartilhem emails, incluindo anexos, de Outlook a qualquer chat ou canal no Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook de share to Teams 

O recurso Compartilhar Teams requer um complemento para Outlook. Esse add-in é instalado automaticamente sempre que um usuário faz logo on no aplicativo Web Teams ou no Teams de área de trabalho.

> [!NOTE]
> Certifique-se de revisar os Outlook [no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e as Regras de Acesso para Cliente no [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para garantir que seus Outlook funcionem corretamente. Além disso, desabilitar experiências conectadas pode impedir que os Outlook de trabalho corretamente. Confira [Experiências conectadas no Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obter mais informações.  

O compartilhamento Teams usa o mesmo mecanismo de transporte que quando um usuário envia emails para um canal. Para o compartilhamento em chats, os emails (incluindo anexos de email) são copiados para o OneDrive. Para compartilhar em canais, emails e anexos são copiados para a pasta **Mensagens de email** em SharePoint.

O complemento do Outlook para Share to Teams usa o conjunto de requisitos 1.7, conforme detalhado na documentação de [complementos](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)do Outlook , que inclui detalhes sobre os complementos do Outlook, os requisitos de ambiente para os complementos do Outlook e os clientes Outlook específicos com suporte com o conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitando ou desabilitando o Compartilhamento para Teams

O Outlook do Share to Teams pode ser desabilitado ou habilitado seletivamente por usuário usando os seguintes cmdlets do PowerShell.

> [!NOTE]
> Desabilitar o complemento só é possível após a instalação do complemento. Se você quiser impor a desabilitação para todos os usuários em seu locatário, execute um script periodicamente.

Para desabilitar o complemento para Outlook usado pelo Share para Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/disable-app?view=exchange-ps). 

Para habilitar o Outlook usado pelo Share para Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/enable-app?view=exchange-ps).

## <a name="browsers-and-single-sign-on"></a>Navegadores e Login Único

O compartilhamento Teams, em clientes de Outlook na Web e Outlook desktop, depende de um WebView do navegador. Consulte [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers. 

> [!IMPORTANT]
> O compartilhamento Teams requer que cookies de terceiros e acesso de armazenamento local sejam habilitados para navegadores dos usuários.

O share to Teams usa o SSO (Single Sign-on), o que significa que os usuários não precisam fornecer suas credenciais ao usar o complemento por meio do Share to Teams. O SSO para Outlook na Web https://outlook.office365.com/owa/extSSO.aspx suporta e responde https://outlook.office.com/owa/extSSO.aspx URLs por padrão. Para domínios de vaidade, os administradores precisam adicionar a URL Azure Active Directory resposta apropriada.