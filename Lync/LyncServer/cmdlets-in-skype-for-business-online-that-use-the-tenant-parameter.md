---
title: Cmdlets no Skype for Business online que usam o parâmetro locatário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 40f325c55415f97822b1e8c9d21a6d2e80e27273
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728011"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlets no Skype for Business online que usam o parâmetro locatário

 


Ao modificar suas configurações de provedor público, você sempre precisa fornecer uma identidade de locatário; Isso é verdadeiro mesmo se você tiver apenas um único locatário. Por exemplo, este comando define o Windows Live como o único provedor público com o qual os usuários podem se comunicar:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Felizmente, você não precisa digitar a ID do locatário (por exemplo, bf19b7db-6960-41e5-a139-2aa373474354) toda vez que executar um destes cmdlets. Em vez disso, você pode recuperar a ID do locatário executando o cmdlet [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , armazenando a ID do locatário em uma variável e, em seguida, usando essa variável quando você chama um dos outros cmdlets. Por exemplo:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Você também pode fazer isso em um único comando ao recuperar a ID do locatário e, em seguida, canalizar esse valor para o cmdlet Set-CsTenantPublicProvider:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Você não precisa especificar a ID do locatário ao chamar o cmdlet **Get-CsTenant** . Esse comando retorna informações sobre o seu locatário:

    Get-CsTenant

Os cmdlets a seguir aceitam uma identidade de locatário. No entanto, nesses casos, o parâmetro é opcional e não precisa ser inserido ao chamar o cmdlet. Em vez disso, o Windows PowerShell inserirá efetivamente a identidade do locatário para você com base no locatário do Skype for Business online ao qual você está conectado:

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

Por exemplo, o cmdlet **Get-CsTenantFederationConfiguration** pode ser chamado usando este comando:

    Get-CsTenantFederationConfiguration

Embora não seja necessário, você pode incluir o parâmetro locatário ao chamar Get-CsTenantFederationConfiguration:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

