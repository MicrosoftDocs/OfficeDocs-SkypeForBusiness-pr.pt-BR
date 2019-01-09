---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Use o PowerShell para permitir ou bloquear o acesso de convidados às equipes do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1e8eaa8722893316f761566a425b7e8ed6f2aaa
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772717"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usar o PowerShell para controlar o acesso de convidados a uma equipe
================================================

Além de usar o centro de administração do Office 365 e o portal do Azure Active Directory, você pode usar o Windows PowerShell para controlar o acesso de convidados. Com o PowerShell, você pode fazer o seguinte:
  
- Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Office 365
    
  
- Permitir que convidados sejam adicionados em todas as equipes e grupos do Office 365
    
  
- Permitir ou bloquear usuários convidados de uma equipe ou grupo do Office 365 específico
    
  
Para obter mais detalhes, veja a seção "Usar o PowerShell para controlar o acesso de convidados" na guia Gerenciar de [Acesso de convidado em Grupos do Office 365](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio. Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam). Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos. Para obter mais informações, consulte [Permitir/bloquear o acesso de convidados nos grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
 
Se desejar bloquear convidados nas equipes mas ainda permitir que os convidados acessem os sites do SharePoint, você pode usar os cmdlets Powershell do Azure Active Directory para desabilitar o parâmetro AllowGuestAccessToGroups no objeto da Empresa, presumindo que o compartilhamento externo esteja ativado para os sites do SharePoint.   

