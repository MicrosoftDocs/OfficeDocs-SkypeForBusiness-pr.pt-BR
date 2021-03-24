---
title: Compartilhar com o Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre o recurso Compartilhar com o Teams, que permite que os usuários compartilhem emails e anexos de email do Outlook para qualquer chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098217"
---
# <a name="share-to-teams-from-outlook"></a>Compartilhar com o Teams do Outlook

Compartilhar com o Teams do Outlook (Compartilhar com o Teams) permite que os usuários compartilhem emails, incluindo anexos, do Outlook para qualquer chat ou canal no Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Complemento do Outlook para Compartilhar com o Teams 

O recurso Compartilhar com o Teams requer um complemento para o Outlook. Esse complemento é instalado automaticamente sempre que um usuário faz logo web no aplicativo Web do Teams ou no cliente da área de trabalho do Teams.

> [!NOTE]
> Revise os [Complementos](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) do Outlook no Exchange Online e as Regras de Acesso para Cliente no [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para garantir que seus complementos para o Outlook funcionem corretamente. Além disso, desabilitar experiências conectadas pode impedir que os complementos do Outlook funcionam corretamente. Confira [Experiências conectadas no Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obter mais informações.  

O compartilhamento com o Teams usa o mesmo mecanismo de transporte que quando um usuário envia emails para um canal. Para o compartilhamento em chats, os emails (incluindo anexos de email) são copiados para o OneDrive do remetente. Para compartilhar em canais, emails e anexos são copiados para a pasta **Mensagens de email** no SharePoint.

O complemento do Outlook para o Share to Teams usa o conjunto de requisitos 1.7, conforme detalhado na documentação de complementos do [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)que inclui detalhes sobre os complementos do Outlook, os requisitos de ambiente para os complementos do Outlook e os clientes específicos do Outlook com suporte com o conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitando ou desabilitando o Compartilhamento no Teams

O complemento do Outlook para o Share to Teams pode ser desabilitado ou habilitado seletivamente por usuário usando os seguintes cmdlets do PowerShell.

> [!NOTE]
> Desabilitar o complemento só é possível após a instalação do complemento. Se você quiser impor a desabilitação para todos os usuários em seu locatário, execute um script periodicamente.

Para desabilitar o complemento do Outlook usado pelo Share to Teams, execute [o cmdlet encontrado aqui](/powershell/module/exchange/disable-app?view=exchange-ps). 

Para habilitar o complemento do Outlook usado pelo Share to Teams, execute [o cmdlet encontrado aqui](/powershell/module/exchange/enable-app?view=exchange-ps).

## <a name="browsers-and-single-sign-on"></a>Navegadores e Login Único

Compartilhar com o Teams, tanto no Outlook na Web quanto nos clientes da área de trabalho do Outlook, depende de um WebView do navegador. Consulte [Navegadores usados pelos Complementos do Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obter detalhes sobre quais clientes usam os navegadores específicos. 

> [!IMPORTANT]
> O compartilhamento com o Teams exige que cookies de terceiros e acesso de armazenamento local sejam habilitados para navegadores dos usuários.

O Compartilhamento para o Teams usa o SSO (Single Sign-on), o que significa que os usuários não precisam fornecer suas credenciais ao usar o complemento por meio do Share to Teams. O SSO para Outlook na Web dá suporte https://outlook.office365.com/owa/extSSO.aspx e https://outlook.office.com/owa/extSSO.aspx responde URLs por padrão. Para domínios de vaidade, os administradores precisam adicionar a URL de resposta apropriada do Azure Active Directory.