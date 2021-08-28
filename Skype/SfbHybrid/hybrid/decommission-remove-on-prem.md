---
title: Desativação de Skype for Business Server
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
description: Instruções para desativá-Skype for Business Server.
ms.openlocfilehash: 349427994a2643fb0a4e5533cc12bc74b2848467
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605720"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Remover a implantação local do Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo descreve como remover sua implantação local Skype for Business local. Esta é a etapa 4 das etapas a seguir para desmantelar seu ambiente local:

- Etapa 1. [Mova todos os usuários necessários do local para o online](decommission-move-on-prem-users.md). 

- Etapa 2. [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- Etapa 3. [Migrar pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md)

- **Etapa 4. Remova sua implantação local Skype for Business local.** (Este artigo)


> [!IMPORTANT] 
> As etapas deste artigo só se aplicam se você estiver usando o Método 2 para gerenciar atributos de usuário, conforme descrito [aqui](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory). Se você estiver usando o Método 1, não use as etapas descritas neste artigo para remover seus Skype for Business servidores. Em vez disso, você pode reimimá-los.

Para concluir as etapas deste artigo, você precisa de privilégios para o grupo Administradores de Esquema e o grupo Enterprise Administrador. Você precisará desses privilégios para desfazer o esquema Skype for Business Server e as alterações no nível da floresta nos Serviços de Domínio do Active Directory. Você também precisará ser membro do grupo RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Preparar para remover a implantação Skype for Business de dados

Depois de mover todas as contas de usuário necessárias para a nuvem, ainda pode haver alguns objetos locais restantes, como contatos e aplicativos que você precisará limpar.

Use as etapas abaixo para limpar esses objetos e certifique-se de que você seja membro do grupo Administrador Local e do grupo RTCUniversalServerAdmins. Observe que o ExUmContacts e PersistantChatEndPoints não estão disponíveis no Skype for Business Server 2019. Se você tiver Skype for Business Server 2019, os cmdlets correspondentes nas etapas abaixo devem ser omitidos.

1. Para verificar se há contatos ou aplicativos associados à implantação Skype for Business Server local, execute os seguintes cmdlets Skype for Business Server PowerShell.

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   Get-CsUnassignedNumber
   ```
2. Revise as listas de saída dos cmdlets na Etapa 1. Em seguida, se os objetos puderem ser removidos, execute o seguinte Skype for Business Server cmdlets do PowerShell:

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   Get-CsUnassignedNumber | Remove-CsUnassignedNumber -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Remover a implantação local do Skype for Business

Após concluir todas as etapas preliminares, você pode remover a Skype for Business de implantação seguindo estas etapas:

1. Remova logicamente a implantação Skype for Business Server, exceto por um único front-end, da seguinte maneira:

   1. Atualize sua Skype for Business Server para ter um único pool front-end:

      1. No Construtor de Topologias, baixe uma nova cópia e navegue até o pool frontend.
      1. Clique com o botão direito no pool e, em seguida, clique em **Editar propriedades**.
      1. Em **Associações, desmarque** **Associar Pool** de Borda (para componentes de mídia) e clique em **OK**.
      1. Se houver mais de um Pool frontend, remova Associações para todos os pools restantes.
      1. Selecione **Ação > Remover Implantação**.
      1. Selecione **Ação > Publicar Topologia**.

    1. Depois de publicar a topologia, conclua as etapas adicionais descritas no assistente.

2. Remova Skype for Business Server diretórios de conferência executando o seguinte Skype for Business Server cmdlet do PowerShell:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Finalize a desinstalação da sua implantação Skype for Business Server executando o seguinte cmdlet Skype for Business Server PowerShell:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Se essa etapa retornar um erro, abra um tíquete de suporte da Microsoft para obter ajuda para remover os objetos que restam.

4. Remova o Ponto de Controle do Serviço do Armazenamento de Gerenciamento Central executando o seguinte Skype for Business Server cmdlet do PowerShell:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Desfazer Skype for Business Server de nível de domínio do Active Directory executando o seguinte Skype for Business Server cmdlet do PowerShell:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Desfazer Skype for Business Server alterações no nível da floresta do Active Directory executando o seguinte Skype for Business Server cmdlet do PowerShell:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Confira também

- [Desativar o ambiente local do Skype for Business](decommission-on-prem-overview.md)

- [Mover todos os usuários necessários do local para o online](decommission-move-on-prem-users.md)

- [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md)

- [Mover pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md)

