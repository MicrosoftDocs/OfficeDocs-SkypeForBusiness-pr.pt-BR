---
title: Mover usuários e pontos de extremidade para a nuvem
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
description: Mova usuários e pontos de extremidade antes de descompactar um ambiente local do Skype for Business.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593871"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>Mover usuários e pontos de extremidade necessários antes de encerrar seu ambiente local

Este artigo descreve como mover usuários e pontos de extremidade de aplicativo necessários para a nuvem da Microsoft antes de encerrar seu ambiente local do Skype for Business. Esta é a etapa 1 das etapas a seguir para desmantelar seu ambiente local:

- **Etapa 1. Mova todos os usuários e pontos de extremidade de aplicativo necessários do local para o online.** (Este artigo.)

- Etapa 2. [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- Etapa 3. [Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Mover todos os usuários necessários do local para a nuvem

Todos os usuários que você continuará a usar depois de concluir a migração devem primeiro ser movidos do local para a nuvem. Você move os usuários usando as ferramentas de administração locais. Para obter detalhes, [consulte Mover usuários entre o local e a nuvem.](move-users-between-on-premises-and-cloud.md)

Embora seja possível que os usuários com contas locais do Skype for Business Server usem o Teams, esses usuários não têm a funcionalidade completa do Teams. Esses usuários não podem interoperar ou federar com qualquer outro usuário que ainda esteja usando o Skype for Business (online ou local). Esses usuários também não podem receber chamadas PSTN em seu cliente do Teams. Portanto, você deve mover esses usuários para online. Esta etapa também garante que todos os contatos ou reuniões criados no Skype for Business Server sejam migrados para o Teams.

Para verificar se há outros usuários em sua implantação local, execute o cmdlet a seguir em uma janela do PowerShell do Skype for Business Server.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Se algum usuário for retornado, revise a saída para determinar se alguma conta deve ser movida para a nuvem e, para esses usuários, siga as etapas [aqui](move-users-between-on-premises-and-cloud.md). Para contas de usuário que não são mais necessárias, execute o seguinte cmdlet do PowerShell do Skype for Business Server:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Executar Disable-CsUser removerá todos os atributos do Skype for Business para todos os usuários que atenderem aos critérios de filtro. Antes de prosseguir, confirme se essas contas não são mais necessárias para avançar.

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>Mover pontos de extremidade de aplicativo híbrido local para o Microsoft 365

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
Agora você está pronto para [desabilitar sua configuração híbrida.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Confira também

- [Desmantelar seu ambiente local do Skype for Business](decommission-on-prem-overview.md)

- [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md)

- [Remover sua implantação local do Skype for Business](decommission-remove-on-prem.md)




