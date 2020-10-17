---
title: Cmdlets no Skype for Business online que usam o parâmetro locatário
description: Cmdlets no Skype for Business online que usam o parâmetro locatário.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546797"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlets no Skype for Business online que usam o parâmetro locatário

 


Ao modificar suas configurações de provedor público, você sempre precisa fornecer uma identidade de locatário; Isso é verdadeiro mesmo que você tenha apenas um único locatário. Por exemplo, este comando define o Windows Live como o único provedor público com o qual os usuários têm permissão para se comunicar:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Felizmente, não é necessário digitar a ID do locatário (por exemplo, bf19b7db-6960-41e5-a139-2aa373474354) sempre que você executar um desses cmdlets. Em vez disso, você pode recuperar a ID do locatário executando o cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , armazenando a ID do locatário em uma variável e usando essa variável ao chamar um dos outros cmdlets. Por exemplo:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Como alternativa, você pode fazer isso em um único comando, recuperando a ID do locatário e canalizando esse valor para o cmdlet Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Você não precisa especificar a ID do locatário ao chamar o cmdlet **Get-CsTenant** . Este comando retorna informações sobre o locatário:

    Get-CsTenant

Os cmdlets a seguir aceitam uma identidade de locatário. No entanto, nesses casos, o parâmetro é opcional e não precisa ser inserido ao chamar o cmdlet. Em vez disso, o Windows PowerShell inserirá efetivamente a identidade do locatário com base no locatário do Skype for Business online ao qual você está atualmente conectado:

  - [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

Por exemplo, o cmdlet **Get-CsTenantFederationConfiguration** pode ser chamado usando este comando:

    Get-CsTenantFederationConfiguration

Embora não seja necessário, você pode incluir o parâmetro locatário ao chamar Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

