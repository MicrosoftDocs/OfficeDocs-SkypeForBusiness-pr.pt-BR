---
title: Desabilitar a migração híbrida para concluir Teams Somente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este artigo inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação da nuvem para Teams e Skype for Business.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453640"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Desabilitar sua configuração híbrida para concluir a migração para Teams Somente 

Este artigo descreve como desabilitar sua configuração híbrida antes de desativar seu ambiente local Skype for Business ambiente. Esta é a etapa 2 das etapas a seguir para desmantelar seu ambiente local:

- Etapa 1. [Mova todos os usuários necessários do local para o online](decommission-move-on-prem-users.md).

- **Etapa 2. Desabilite sua configuração híbrida.** (Este artigo)

- Etapa 3. [Migrar pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md).

- Etapa 4. [Remova sua implantação local Skype for Business .](decommission-remove-on-prem.md)

> [!NOTE]
> As etapas 2 e 3 devem ser feitas na mesma janela de manutenção, pois quaisquer pontos de extremidade de aplicativo híbrido existentes não serão descobertos entre as etapas 2 e a conclusão da etapa 3.


## <a name="summary"></a>Resumo

Depois de atualizar todos os usuários do Skype for Business local para o Teams somente no Microsoft 365, você poderá desativá-la Skype for Business implantação local.

Antes de desativar a implantação Skype for Business local e remover qualquer hardware, você deve separar logicamente a implantação local do Microsoft 365 desabilitando o híbrido. Desabilitar híbrido consiste nas quatro etapas a seguir:

1. [Atualizar registros DNS para apontar para Microsoft 365](#update-dns-to-point-to-microsoft-365).

2. [Altere o modo de coexistência para sua organização para Teams Somente](#change-the-coexistence-mode-for-your-organization-to-teams-only).

3. [Desabilitar o espaço de endereço sip compartilhado (também conhecido como "domínio dividido") na organização Microsoft 365 .](#disable-shared-sip-address-space-in-microsoft-365-organization)

4. [Desabilitar a comunicação entre o local e o Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

Essas etapas separam logicamente sua implantação local do Skype for Business Server do Microsoft 365 e garantem que sua organização está totalmente Teams Somente. Depois de concluir essas etapas, você pode desativá-la Skype for Business implantação local usando um dos dois métodos referenciados em Decidir como gerenciar atributos após o [descomissionamento](cloud-consolidation-managing-attributes.md).

> [!Important] 
> Depois que essa separação lógica for concluída, os atributos msRTCSIP do Active Directory local ainda terão valores e continuarão a sincronizar por meio do Azure AD Conexão no Azure AD. Como você desativa o ambiente local depende se você pretende deixar esses atributos no lugar ou primeiro descompactá-los do Active Directory local. Esteja ciente de que limpar os atributos msRTCSIP locais depois que você tiver migrado do local pode resultar em perda de serviço para os usuários! Detalhes e trocas das duas abordagens de desativação são descritos em Decidir como gerenciar atributos [após a desativação.](cloud-consolidation-managing-attributes.md)

## <a name="update-dns-to-point-to-microsoft-365"></a>Atualizar DNS para apontar para Microsoft 365

O DNS externo da organização para a organização local precisa ser atualizado para que os registros Skype for Business apontem para Microsoft 365 em vez da implantação local. 

Além disso, os registros CNAME para meet ou dialin (se presente) podem ser excluídos. Por fim, quaisquer registros DNS para Skype for Business em sua rede interna devem ser removidos.

Para obter detalhes sobre como atualizar registros DNS, consulte [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>Altere o modo de coexistência para que sua organização Teams Somente

Esta etapa garante que qualquer novo usuário em sua organização seja sempre criado como um Teams usuário único. 

Tentar alterar o modo de locatário para Teams Somente verificará automaticamente a existência de quaisquer registros DNS locais que possam ter sido perdidas na etapa 1 e identificar esses registros na saída. Alterar o modo de locatário para Teams somente terá êxito até que todos os registros DNS da sua organização sejam atualizados. 

Para alterar o modo de locatário para Teams execute somente o seguinte comando de uma janela Teams PowerShell.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

Como alternativa, você pode usar o Centro de Administração Teams para alterar o modo de coexistência do locatário para o TeamsOnly, em "Configurações de toda a organização" -> "atualização Teams".    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>Desabilitar o espaço de endereço sip compartilhado Microsoft 365 organização
    
Para desabilitar o espaço de endereço sip compartilhado, execute o seguinte comando de uma Teams do PowerShell.

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>Desabilitar a comunicação entre o local e o Microsoft 365

Para desabilitar a comunicação entre o ambiente local e o Microsoft 365, execute o seguinte comando de uma janela local do PowerShell:

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>Confira também

- [Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)

- [Desativar o ambiente local do Skype for Business](decommission-on-prem-overview.md)

