---
title: Mover pontos de extremidade de aplicativo híbrido para a nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Mova pontos de extremidade de aplicativo hirido antes de encerrar um ambiente local do Skype for Business.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656872"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Mover pontos de extremidade do aplicativo hirido antes de encerrar seu ambiente local

Este artigo descreve como mover pontos de extremidade de aplicativo híbrido necessários para a nuvem da Microsoft antes de encerrar seu ambiente local do Skype for Business. Esta é a etapa 3 das etapas a seguir para desmantelar seu ambiente local:

- Etapa 1. [Mover todos os usuários necessários do local para o online](decommission-move-on-prem-users.md)

- Etapa 2. [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- **Etapa 3. Mova os pontos de extremidade do aplicativo híbrido do local para o online.** (Este artigo)

- Etapa 4. [Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Mover todos os pontos de extremidade de aplicativo híbrido necessários do local para o online

Antes de poder mover esses pontos de extremidade para online, você deve garantir que os registros DNS atualizados apontem para o Microsoft 365 para todos os domínios sip usados pelos pontos de extremidade. Não é possível criar contas de recursos online se os registros DNS apontarem para o local. Para obter mais informações, consulte [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).

1. Recupere e exporte configurações de ponto de extremidade de aplicativo híbrido local executando o seguinte comando local do Skype for Business Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Crie e licencie novas Contas [de](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) Recursos no Microsoft 365 para substituir os pontos de extremidade de aplicativo híbrido locais existentes.

3. Associe as novas Contas de Recursos aos pontos de extremidade do aplicativo híbrido existentes.

4. Remova números de telefone definidos nos pontos de extremidade do aplicativo híbrido local executando o seguinte comando do PowerShell do Skype for Business Server local:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Como é possível que os números de telefone dessas contas fossem gerenciados no Microsoft 365 em vez de no local, execute o seguinte comando no Skype for Business Online PowerShell:

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. Atribua números de telefone às novas Contas de Recursos criadas na Etapa 2. Para obter mais informações sobre como atribuir um número de telefone a uma conta de recurso, consulte o seguinte artigo: [Atribuir um número de serviço](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).

7. Exclua os pontos de extremidade locais executando o seguinte comando local do Skype for Business Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Agora você está pronto para remover sua implantação local do [Skype for Business.](decommission-remove-on-prem.md)

## <a name="see-also"></a>Confira também

- [Desativar o ambiente local do Skype for Business](decommission-on-prem-overview.md)

- [Mover todos os usuários necessários do local para o online](decommission-move-on-prem-users.md)

- [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md)

- [Remover a implantação local do Skype for Business](decommission-remove-on-prem.md)




