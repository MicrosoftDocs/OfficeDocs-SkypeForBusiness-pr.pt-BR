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
appliesto:
- Microsoft Teams
ms.openlocfilehash: db4b3adabecf147f5adf9cadb9891892b5a82e5a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606220"
---
# <a name="share-to-teams-from-outlook"></a>Compartilhar com o Teams do Outlook

Compartilhar com o Teams do Outlook (Compartilhar com o Teams) permite que os usuários compartilhem emails, incluindo anexos, do Outlook para qualquer chat ou canal no Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Suplemento do Outlook para Compartilhar com o Teams 

O recurso Compartilhar com o Teams requer um suplemento para o Outlook. Esse suplemento é instalado automaticamente sempre que um usuário faz logon no aplicativo Web do Teams ou no cliente da área de trabalho do Teams.

> [!NOTE]
> Examine os [Suplementos do Outlook no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e as Regras de Acesso do Cliente no [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para garantir que os suplementos do Outlook funcionem corretamente. Além disso, desabilitar experiências conectadas pode impedir que os suplementos do Outlook funcionem corretamente. Confira [experiências conectadas no Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obter mais informações.  

O compartilhamento com o Teams usa o mesmo mecanismo de transporte que quando um usuário envia um canal por email. Para compartilhar chats, emails (incluindo anexos de email) são copiados para o OneDrive do remetente. Para compartilhamento com canais, emails e anexos são copiados para a pasta **Mensagens de email** no SharePoint.

O suplemento do Outlook para Compartilhar com o Teams usa o conjunto de requisitos 1.7, conforme detalhado na documentação de [suplementos do Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), que inclui detalhes sobre suplementos do Outlook, requisitos de ambiente para suplementos do Outlook e os clientes específicos do Outlook que têm suporte com o conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitando ou desabilitando o compartilhamento com o Teams

O suplemento do Outlook para Compartilhar com o Teams pode ser desabilitado seletivamente ou habilitado por usuário usando os cmdlets do PowerShell a seguir.

> [!NOTE]
> Desabilitar o suplemento só é possível após a instalação do suplemento. Se você quiser impor a desabilitação para todos os usuários em seu locatário, execute um script periodicamente.

Para desabilitar o suplemento do Outlook usado pelo Share to Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/disable-app).

Para habilitar o suplemento do Outlook usado pelo Share to Teams, execute o [cmdlet encontrado aqui](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Navegadores e Logon Único

Compartilhar com o Teams, tanto Outlook na Web clientes da área de trabalho do Outlook, depende de um WebView do navegador. Consulte [Navegadores usados pelos Suplementos do Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obter detalhes sobre quais clientes usam quais navegadores específicos. 

> [!IMPORTANT]
> Compartilhar com o Teams requer que cookies de terceiros e acesso de armazenamento local sejam habilitados para navegadores dos usuários.

Compartilhar com o Teams usa o SSO (logon único), o que significa que os usuários não precisam fornecer suas credenciais ao usar o suplemento por meio do Compartilhamento com o Teams. O SSO para Outlook na Web dá suporte <https://outlook.office365.com/owa/extSSO.aspx> a <https://outlook.office.com/owa/extSSO.aspx> URLs de resposta e suporte por padrão. Para domínios personalizados, os administradores precisam adicionar a URL de resposta apropriada do Azure Active Directory.
