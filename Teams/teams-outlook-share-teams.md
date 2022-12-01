---
title: Compartilhar com o Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre o recurso Compartilhar com o Teams, que permite que os usuários compartilhem emails e anexos de email do Outlook para qualquer chat ou canal no Teams.
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f8334f8dbdbebce17dea4a8a4ebc8ebf798b79
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198483"
---
# <a name="share-to-teams-from-outlook"></a>Compartilhar com o Teams do Outlook

Compartilhar com o Teams do Outlook (Compartilhar para o Teams) permite que os usuários compartilhem emails, incluindo anexos, do Outlook a qualquer chat ou canal no Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Suplemento do Outlook para Compartilhar no Teams 

O recurso Compartilhar com o Teams requer um suplemento para o Outlook. Esse suplemento é instalado automaticamente sempre que um usuário faz logon no aplicativo Web do Teams ou no cliente da área de trabalho do Teams.

> [!NOTE]
> Examine os [suplementos do Outlook em Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e [regras de acesso ao cliente em Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para garantir que seus suplementos para o Outlook funcionem corretamente. Além disso, desabilitar experiências conectadas pode impedir que os suplementos do Outlook funcionem corretamente. Consulte [Experiências conectadas no Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obter mais informações. Não há suporte para caixas de correio compartilhadas pelo suplemento. 

Compartilhar com o Teams usa o mesmo mecanismo de transporte que quando um usuário envia emails a um canal. Para compartilhar chats, os emails (incluindo anexos de email) são copiados para o OneDrive do remetente. Para compartilhamento em canais, emails e anexos são copiados para a pasta **mensagens Email** no SharePoint.

O suplemento do Outlook para Compartilhar com o Teams usa o conjunto de requisitos 1.7, conforme detalhado na [documentação de suplementos do Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), que inclui detalhes sobre suplementos do Outlook, requisitos de ambiente para suplementos do Outlook e os clientes específicos do Outlook com suporte com o conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitar ou desabilitar o Share para o Teams

O suplemento do Outlook para Compartilhar com o Teams pode ser desabilitado seletivamente ou habilitado por usuário usando os seguintes cmdlets do PowerShell.

> [!NOTE]
> Desabilitar o suplemento só é possível após a instalação do suplemento. Se você quiser impor a desabilitação para todos os usuários em seu locatário, execute um script periodicamente.

Para desabilitar o suplemento do Outlook usado pelo Share to Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/disable-app).

Para habilitar o suplemento para o Outlook usado pelo Share to Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Navegadores e Logon Único

O compartilhamento com o Teams, em clientes da área de trabalho do Outlook na Web e do Outlook, depende de um WebView do navegador. Consulte [Navegadores usados pelos Suplementos do Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obter detalhes sobre quais clientes usam quais navegadores específicos. 

> [!IMPORTANT]
> O compartilhamento com o Teams requer que cookies de terceiros e acesso ao armazenamento local sejam habilitados para os navegadores dos usuários.

O compartilhamento com o Teams usa o SSO (Logon Único), o que significa que os usuários não precisam fornecer suas credenciais ao usar o suplemento por meio do Share to Teams. O SSO para Outlook na Web dá suporte <https://outlook.office365.com/owa/extSSO.aspx> e <https://outlook.office.com/owa/extSSO.aspx> responde URLs por padrão. Para domínios de vaidade, os administradores precisam adicionar a URL de resposta apropriada do Azure Active Directory.
