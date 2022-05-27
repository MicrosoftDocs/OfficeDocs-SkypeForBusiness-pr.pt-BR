---
title: Compartilhar com Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre o recurso Compartilhar Teams, que permite que os usuários compartilhem emails e anexos de email do Outlook para qualquer chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682022"
---
# <a name="share-to-teams-from-outlook"></a>Compartilhar com Teams do Outlook

Compartilhar com Teams do Outlook (Compartilhar para Teams) permite que os usuários compartilhem emails, incluindo anexos, do Outlook a qualquer chat ou canal no Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook suplemento para Compartilhar para Teams 

O recurso Compartilhar Teams requer um suplemento para Outlook. Esse suplemento é instalado automaticamente sempre que um usuário faz logon no aplicativo Web Teams ou no Teams da área de trabalho.

> [!NOTE]
> Examine os [Suplementos do Outlook no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e nas Regras de Acesso do Cliente no [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para verificar se os suplementos para Outlook funcionam corretamente. Além disso, desabilitar experiências conectadas pode impedir que os suplementos Outlook funcionem corretamente. Consulte [Experiências conectadas no Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obter mais informações.  

Compartilhar com Teams usa o mesmo mecanismo de transporte que quando um usuário envia emails para um canal. Para compartilhar chats, os emails (incluindo anexos de email) são copiados para a conta do OneDrive. Para compartilhamento com canais, emails e anexos são copiados para a pasta **Mensagens de email** SharePoint.

O suplemento Outlook para Compartilhar com o Teams usa o conjunto de requisitos 1.7, conforme detalhado na documentação de [suplementos do Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), que inclui detalhes sobre suplementos do Outlook, requisitos de ambiente para suplementos do Outlook e os clientes específicos do Outlook que têm suporte com o conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitando ou desabilitando o Compartilhamento para Teams

O Outlook do Share to Teams pode ser desabilitado ou habilitado seletivamente por usuário usando os cmdlets do PowerShell a seguir.

> [!NOTE]
> Desabilitar o suplemento só é possível após a instalação do suplemento. Se você quiser impor a desabilitação para todos os usuários em seu locatário, execute um script periodicamente.

Para desabilitar o suplemento para Outlook usado pelo Share to Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/disable-app).

Para habilitar o suplemento para Outlook usado pelo Share to Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Navegadores e Logon Único

Compartilhar com Teams, em clientes Outlook na Web e Outlook desktop, depende de um WebView do navegador. Consulte [Navegadores usados Office suplementos](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obter detalhes sobre quais clientes usam quais navegadores específicos. 

> [!IMPORTANT]
> Compartilhar com Teams requer que os cookies de terceiros e o acesso ao armazenamento local sejam habilitados para navegadores dos usuários.

O Share to Teams usa o SSO (logon único), o que significa que os usuários não precisam fornecer suas credenciais ao usar o suplemento por meio do Share to Teams. O SSO para Outlook na Web dá suporte <https://outlook.office365.com/owa/extSSO.aspx> a <https://outlook.office.com/owa/extSSO.aspx> URLs de resposta e suporte por padrão. Para domínios personalizados, os administradores precisam adicionar a URL Azure Active Directory resposta apropriada.
