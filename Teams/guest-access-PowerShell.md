---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Use o PowerShell para permitir ou bloquear o acesso de convidados às equipes do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b429d4e2411e697c4e3357ebd7b5fc66ab27376
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35220882"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usar o PowerShell para controlar o acesso de convidados a uma equipe
================================================

Além de usar o centro de administração do Microsoft 365 e o portal do Azure Active Directory (Azure AD), você pode usar o Windows PowerShell para controlar o acesso de convidados. Com o PowerShell, você pode fazer o seguinte:
  
- Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Office 365

- Permitir que os convidados sejam adicionados a todas as equipes e grupos do Office 365

- Permitir ou bloquear usuários convidados de uma equipe ou grupo do Office 365 específico

Para obter detalhes, consulte "usar o PowerShell para controlar o acesso de convidado" em [gerenciar o acesso de convidados nos grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).
  
Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio. Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam). Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos. Para obter mais informações, consulte [permitir/bloquear o acesso de convidados a grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Se quiser bloquear convidados no Microsoft Teams e ainda quiser permitir que eles acessem sites do SharePoint, você pode usar cmdlets do PowerShell do Azure AD para desabilitar o parâmetro AllowGuestsToAccessGroups no objeto Company, pressupondo que o compartilhamento externo esteja ativado para sites do SharePoint .

## <a name="guest-access-vs-external-access"></a>Acesso de convidado versus acesso externo

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
