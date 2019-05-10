---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
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
ms.openlocfilehash: 0efb3a8054008d179b9d2e7e674b3482fe62a32c
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865086"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usar o PowerShell para controlar o acesso de convidados a uma equipe
================================================

Além de usar o Centro de administração do Microsoft 365 e o portal do Azure Active Directory, você pode usar o Windows PowerShell para controlar o acesso de convidado. Com o PowerShell, você pode fazer o seguinte:
  
- Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Office 365
    
- Permitir que convidados sejam adicionados em todas as equipes e grupos do Office 365
      
- Permitir ou bloquear usuários convidados de uma equipe ou grupo do Office 365 específico
    
Para obter detalhes, consulte a seção "Usar o PowerShell para controlar o acesso de convidado" na guia gerenciar de [acesso de convidado em grupos do Office 365](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio. Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam). Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos. Para obter mais informações, consulte [Permitir/bloquear o acesso de convidados nos grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Se você deseja bloquear convidados em equipes e ainda quiser permitir que eles acessem sites do SharePoint, você pode usar cmdlets do Azure Active Directory Powershell para desabilitar o parâmetro AllowGuestsToAccessGroups no objeto empresa, supondo que o compartilhamento externo é ativado para Sites do SharePoint.   

## <a name="guest-access-vs-external-access"></a>Acesso de convidado versus acesso externo

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
