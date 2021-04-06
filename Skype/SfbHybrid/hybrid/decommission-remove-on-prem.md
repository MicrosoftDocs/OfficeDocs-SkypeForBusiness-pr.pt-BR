---
title: Desativação do Skype for Business Server
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
description: Instruções para desativação do Skype for Business Server.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593870"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Remover sua implantação local do Skype for Business

Este artigo descreve como remover sua implantação local do Skype for Business. Esta é a etapa 3 das etapas a seguir para desmantelar seu ambiente local:

- Etapa 1. Mova todos os usuários e pontos de extremidade de aplicativo [necessários do local para o online](decommission-move-on-prem-users.md). 

- Etapa 2. [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- **Etapa 3. Remova sua implantação local do Skype for Business.** (Este artigo)


> [!IMPORTANT] 
> As etapas deste artigo só se aplicam se você estiver usando o Método 2 para gerenciar atributos de usuário, conforme descrito [aqui](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory). Se você estiver usando o Método 1, não use as etapas descritas neste artigo para remover seus servidores do Skype for Business. Em vez disso, você pode reimimá-los.

Para concluir as etapas deste artigo, você precisa de privilégios para o grupo Administradores de Esquema e para o grupo Administrador empresarial. Você precisará desses privilégios para desfazer o esquema do Skype for Business Server e as alterações no nível da floresta nos Serviços de Domínio do Active Directory. Você também precisará ser membro do grupo RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Preparar para remover a implantação do Skype for Business

Depois de mover todas as contas de usuário necessárias para a nuvem, ainda pode haver alguns objetos locais restantes, como contatos e aplicativos que você precisará limpar.

Use as etapas abaixo para limpar esses objetos e certifique-se de que você seja membro do grupo Administrador Local e do grupo RTCUniversalServerAdmins. Observe que o ExUmContacts e PersistantChatEndPoints não estão disponíveis no Skype for Business Server 2019. Se você tiver o Skype for Business Server 2019, os cmdlets correspondentes nas etapas abaixo devem ser omitidos.

1. Para verificar se há contatos ou aplicativos associados à implantação local do Skype for Business Server, execute os seguintes cmdlets do PowerShell do Skype for Business Server.

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
   ```
2. Revise as listas de saída dos cmdlets na Etapa 1. Em seguida, se os objetos puderem ser removidos, execute os seguintes cmdlets do PowerShell do Skype for Business Server:

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
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Remover sua implantação local do Skype for Business

Após concluir todas as etapas preliminares, você pode remover a implantação do Skype for Business seguindo estas etapas:

1. Remova logicamente a implantação do Skype for Business Server, exceto por um único front-end, da seguinte maneira:

   a. Atualize sua topologia do Skype for Business Server para ter um único pool front-end:

     - No Construtor de Topologias, baixe uma nova cópia e navegue até o pool frontend.
     - Clique com o botão direito no pool e, em seguida, clique em **Editar propriedades**.
     - Em **Associações, desmarque** **Associar Pool** de Borda (para componentes de mídia) e clique em **OK**.
     - Se houver mais de um Pool frontend, remova Associações para todos os pools restantes.
     - Selecione **Ação > Remover Implantação**.
     - Selecione **Ação > Publicar Topologia**.

    b. Depois de publicar a topologia, conclua as etapas adicionais descritas no assistente.

2. Remova os diretórios de conferência do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Finalize a desinstalação da implantação do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Se essa etapa retornar um erro, abra um tíquete de suporte da Microsoft para obter ajuda para remover os objetos que restam.

4. Remova o Ponto de Controle do Serviço do Armazenamento de Gerenciamento Central executando o seguinte cmdlet do PowerShell do Skype for Business Server:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Desfazer alterações no nível da floresta do Domínio do Active Directory do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Desfazer alterações de esquema de Domínio do Active Directory do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Confira também

- [Desmantelar seu ambiente local do Skype for Business](decommission-on-prem-overview.md)

- [Mover usuários e pontos de extremidade para a nuvem](decommission-move-on-prem-users.md)

- [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md)














