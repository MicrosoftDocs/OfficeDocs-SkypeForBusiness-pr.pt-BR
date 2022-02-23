---
title: Migrar pontos de extremidade de aplicativo híbrido para a nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Migre pontos de extremidade de aplicativo hirido antes de descomissionar um ambiente Skype for Business local.
ms.openlocfilehash: 74e0ef935c993f6e39b08759d3beb69e0c5c7673
ms.sourcegitcommit: d8dba15c520de3894d1781e17acb2c75fb38ed49
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62921849"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Migrar pontos de extremidade de aplicativo híbrido antes de encerrar seu ambiente local

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo descreve como mover os pontos de extremidade de aplicativo híbrido necessários para a nuvem da Microsoft antes de desativá-los Skype for Business ambiente. Esta é a etapa 3 das etapas a seguir para desmantelar seu ambiente local:

- Etapa 1. [Mover todos os usuários necessários do local para o online](decommission-move-on-prem-users.md)

- Etapa 2. [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- **Etapa 3. Migrar pontos de extremidade de aplicativo híbrido do local para o online.** (Este artigo)

- Etapa 4. [Remova sua implantação local Skype for Business local](decommission-remove-on-prem.md).


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Migrar todos os pontos de extremidade de aplicativo híbrido necessários do local para o online

Antes de mover esses pontos de extremidade para online, você deve garantir que os registros DNS atualizados apontem para Microsoft 365 para todos os domínios sip usados pelos pontos de extremidade. Esteja ciente de que, depois de atualizar o DNS para apontar para Microsoft 365, todos os pontos de extremidade de aplicativo híbrido existentes não serão mais descobertos até que você conclua esta etapa. Como esta etapa (criar contas de recursos online) não será possível se os registros DNS apontarem para o local, você deve planejar realizar as etapas 2 e 3 na mesma janela de manutenção. Para obter mais informações, consulte [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

1. Recupere e exporte configurações de ponto de extremidade de aplicativo híbrido local executando o seguinte comando local Skype for Business Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Crie e licencie novas [contas de](/microsoftteams/manage-resource-accounts) recursos Microsoft 365 substituir os pontos de extremidade do aplicativo híbrido local existentes.

3. Associe as novas Contas de Recursos aos pontos de extremidade do aplicativo híbrido existentes.

4. Remova números de telefone definidos nos pontos de extremidade do aplicativo híbrido local executando o seguinte comando local Skype for Business Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Como é possível que os números de telefone dessas contas fossem gerenciados no Microsoft 365 em vez de no local, execute o seguinte comando no Teams PowerShell:

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

6. Atribua números de telefone às novas Contas de Recursos criadas na Etapa 2. Para obter mais informações sobre como atribuir um número de telefone a uma conta de recurso, consulte o seguinte artigo: [Atribuir um número de serviço](/microsoftteams/manage-resource-accounts).

7. Exclua os pontos de extremidade locais executando o seguinte comando local Skype for Business Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Agora você está pronto para remover sua implantação local [Skype for Business local](decommission-remove-on-prem.md).

## <a name="see-also"></a>Confira também

- [Desativar o ambiente local do Skype for Business](decommission-on-prem-overview.md)

- [Mover todos os usuários necessários do local para o online](decommission-move-on-prem-users.md)

- [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md)

- [Remover a implantação local do Skype for Business](decommission-remove-on-prem.md)

- [Criar um atendimento automático por meio de cmdlets](/microsoftteams/create-a-phone-system-auto-attendant-via-cmdlets)




