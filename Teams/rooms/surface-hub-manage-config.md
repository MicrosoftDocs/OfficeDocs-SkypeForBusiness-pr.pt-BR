---
title: Gerenciar Microsoft Teams configuração no Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Gerenciar Microsoft Teams configurações no Surface Hub usando Microsoft Intune e Windows Designer de Configuração
ms.openlocfilehash: 70295a22524dc702832a729dc7e631c49b206053
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015261"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gerenciar Microsoft Teams configurações no Surface Hub

Você pode gerenciar Microsoft Teams configurações em um Surface Hub usando Windows Designer de Configuração ou Microsoft Intune no Microsoft Endpoint Manager. O conhecimento Windows designer de configuração ou Microsoft Intune é necessário para fazer alterações nas Teams configurações. Para obter mais informações sobre essas opções, consulte os seguintes artigos:

- [Criar um pacote de provisionamento para Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [O que é Microsoft Intune de dispositivos?](/mem/intune/remote-actions/device-management)

Windows Designer de Configuração é uma boa opção se você tiver apenas alguns dispositivos Surface Hub e você puder acessá-los facilmente. Se você tiver muitos Surface Hubs ou se eles estão em locais remotos, use Microsoft Intune no Microsoft Endpoint Manager se estiver implantado em sua organização. Independentemente do método escolhido, você precisa criar um arquivo de configuração XML para fazer alterações nas configurações Teams no Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Teams de arquivo de configuração

Teams configuração em um Surface Hub é definida usando um arquivo XML. O arquivo XML contém todas as configurações que podem ser usadas para controlar como Teams funciona. Tanto Windows Designer de Configuração quanto Microsoft Intune usar a mesma sintaxe XML. Veja um exemplo do arquivo XML Teams configuração:

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

A tabela a seguir descreve todas as configurações disponíveis no arquivo de configuração:

| Pai                  | Elemento                                   | Atributo | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nenhum                    | `<SurfaceHubSettings>`                    |           | Contém todos os elementos de configuração Teams configuração em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se Surface Hub que ele está disponível para Bluetooth conexões.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se as Teams aceitarão automaticamente reuniões baseadas em proximidade.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contém todos os elementos de configuração para Reuniões Coordenadas.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se o Teams está configurado para participar de Reuniões Coordenadas com outros dispositivos.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Esta é uma lista separada por vírgulas de UPNs para cada dispositivo de sala Teams ou Surface Hub de onde o dispositivo deve aceitar solicitações de junção de reunião ou para quais solicitações de junção de reunião devem ser enviadas.<br>Valores aceitos: cadeia de caracteres                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contém elementos de configuração de áudio e vídeo para reuniões coordenadas                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controla a configuração de áudio para Teams em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina em qual dispositivo o microfone estará ativo quando uma reunião for iniciada. Somente um dispositivo (normalmente um dispositivo Salas do Teams) pode ter esse campo definido como enquanto o restante dos dispositivos deve ter esse campo definido para evitar eco de áudio e `true` `false` comentários.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se os participantes de uma reunião podem alternar ou desligar o microfone. Dispositivos nos quais **o padrão** de áudio é definido devem ter essa configuração definida para que os participantes não possam ativar acidentalmente um microfone e causar eco de áudio `false` ou `false` comentários.<p>Se **o padrão de** áudio estiver definido como , essa configuração será ignorada e os participantes poderão `true` silenciar ou desativar o microfone.<br>Valores aceitos: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controla a configuração de vídeo para Teams em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina em qual dispositivo a câmera estará ativa quando uma reunião for iniciada. Para a melhor experiência, recomendamos que apenas o dispositivo Salas do Teams seja definido como enquanto todos os outros `true` dispositivos estão definidos como `false` .<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se os participantes de uma reunião podem alternar ou desligar a câmera. Você pode definir isso como em qualquer outro dispositivo no evento em que os participantes do evento quiserem compartilhar diferentes perspectivas de vídeo (como se um participante estiver usando o quadro de Surface Hub `true` de vídeo). Se você não quiser que os participantes a liguem ou desliguem uma câmera em um dispositivo, de definir isso como `false` .<p> Se **o padrão de** vídeo estiver definido como , essa configuração será ignorada e os participantes poderão ativar ou desativar a `true` câmera.<br>Valores aceitos: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Aplicar Teams configurações a Surface Hub

Aplique ou atualize Teams configurações no Surface Hub usando o Designer de Configuração Windows ou Microsoft Intune no Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usar Windows Designer de Configuração

Você pode usar Windows Designer de Configuração para criar um pacote de provisionamento que você pode usar para aplicar Teams configurações aos surface hubs. Você colará o arquivo XML criado acima no Windows Configuration Designer para criar o pacote de provisionamento.

> [!IMPORTANT]
> Se você já aplicou Teams configuração ao seu Surface Hub usando um pacote de provisionamento e deseja alterá-lo, você precisa remover o pacote de provisionamento existente primeiro. Para obter mais informações, [consulte Remove a provisioning package created by Windows Configuration Designer](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Faça o seguinte para criar o pacote de provisionamento no Windows Configuration Designer:

1. Instale Windows Designer de Configuração no Windows Store no computador local e abra-o
2. Selecione **Provisionar Surface Hub dispositivos** e **alternar para editor avançado**
3. Na próxima tela, **expanda WindowsTeamSettings**  >  **Teams** e selecione **Configurações**
4. No campo ao lado **de Configurações** no painel intermediário, colar a única linha de XML que você criou acima
5. Selecione **Exportar**  >  **pacote de provisionamento**
6. Forneça um nome para o pacote de provisionamento em **Nome** e selecione **Next**  >  **Next**
7. Especifique um local para salvar o pacote de provisionamento e selecione **Next**
8. Selecione **Criar** para criar o pacote de provisionamento e, em seguida, **Concluir**

Por fim, depois de criar o pacote de provisionamento, faça o seguinte para aplicar o pacote de provisionamento ao seu Surface Hub:

1. Salve o pacote de provisionamento criado acima em uma unidade USB
2. Insira a unidade USB em sua Surface Hub
3. Em seu Surface Hub, abra o menu Iniciar, selecione Todos os **aplicativos** e selecione **Configurações**
4. Forneça seu nome de usuário e senha do administrador e selecione **Sim**
5. Vá para **Surface Hub**, **Gerenciamento de dispositivos,** Adicionar ou remover um pacote **de provisionamento** e, em seguida, **Adicionar um pacote**
6. Em **Selecionar um pacote,** selecione **Adicionar** ao lado do pacote de provisionamento e reinicie seu Surface Hub

### <a name="use-microsoft-intune"></a>Use Microsoft Intune

Se os Surface Hubs são gerenciados usando Microsoft Intune gerenciamento de pontos de extremidade da Microsoft, você pode usá-lo para aplicar Teams configurações aos surface hubs. Você criará um novo perfil de configuração e colará o arquivo XML criado acima nele.

> [!IMPORTANT]
> Os Surface Hubs precisam estar em um grupo de dispositivos para que o Microsoft Intune possa identificar a quais dispositivos aplicar o perfil de configuração. Para obter informações sobre como criar um grupo de dispositivos, consulte [Adicionar grupos para organizar usuários e dispositivos.](/mem/intune/fundamentals/groups-add)

Faça o seguinte para criar um perfil de configuração para aplicar Teams configurações aos Surface Hubs:

1. Entre no Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Navegue até **Perfis**  >  **de Configuração de Dispositivos** e selecione **Criar perfil**
3. Em **Plataforma**, selecione **Windows 10 e posterior**
4. Em **Perfil,** selecione **Personalizado** e clique em **Criar**
5. Na guia **Noções Básicas,** em **Nome**, forneça um nome descritivo para seu perfil de configuração e selecione **Next**
6. Na guia **Configuração,** selecione **Adicionar**
7. No painel **Adicionar** linha, faça o seguinte:
    1. Forneça um nome descritivo e, opcionalmente, uma descrição da configuração Teams que você está adicionando
    2. No **OMA-URI,** insira `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Em **Tipo de dados,** selecione **Cadeia de caracteres (arquivo XML)**
    4. Abra o navegador de arquivos, selecione o arquivo XML criado acima e **Abra**
8. Selecione **Adicionar** e, em **seguida, Próximo**
9. Na guia **Atribuições,** certifique-se de **atribuir está** definido como **Grupos Selecionados**
10. Em **Grupos Selecionados**, selecione **Selecionar grupos** para incluir e escolher o grupo que contém seus Surface Hubs e selecione **Selecionar**
11. Selecione **Próximo**, **Próximo**
12. Na revisão **+ criar,** selecione **Criar**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Remover Teams configurações de um Surface Hub

Remova Teams configuração no Surface Hub usando o Windows Configuration Designer ou Microsoft Intune no Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Remover um pacote de provisionamento criado pelo Windows Configuration Designer

Se você aplicou Teams configurações a um Surface Hub usando um pacote de provisionamento criado pelo designer de configuração Windows, use as etapas a seguir para remover o pacote e suas configurações:

1. Em seu Surface Hub, abra o menu Iniciar, selecione Todos os **aplicativos** e selecione **Configurações**
2. Forneça seu nome de usuário e senha do administrador e selecione **Sim**
3. Vá para **Surface Hub**, **Gerenciamento de dispositivos** e **adicione ou remova um pacote de provisionamento**
4. Ao lado do pacote de provisionamento que você deseja remover, selecione **Remover**
5. Vá para **o Surface Hub** e, em seguida, **aplicativos & recursos**
6. Encontre **Microsoft Teams para Surface Hub** e selecione Opções **Avançadas**
7. Selecione **Redefinir** e **redefinir** novamente
8. Reinicie seu Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Remover configurações aplicadas por Microsoft Intune

Se você aplicou Teams configurações a um Surface Hub usando Microsoft Intune gerenciamento de pontos de extremidade da Microsoft, use as etapas a seguir para remover o perfil de configuração e suas configurações:

1. Entre no Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Navegar até **perfis de**  >  **configuração de dispositivos**
3. Selecione o perfil de configuração que contém as configurações de Reunião Coordenadas que você deseja remover
4. Na página detalhes do perfil de configuração, selecione **Excluir** **e,** em seguida, OK

Depois de remover o perfil de configuração que continha as configurações de Reunião Coordenadas do seu Surface Hub, use as etapas a seguir para redefinir o aplicativo Teams no Surface Hub:

1. Em seu Surface Hub, abra o menu Iniciar, selecione Todos os **aplicativos** e selecione **Configurações**
2. Forneça seu nome de usuário e senha do administrador e selecione **Sim**
3. Vá para **o Surface Hub** e, em seguida, **aplicativos & recursos**
4. Encontre **Microsoft Teams para Surface Hub** e selecione Opções **Avançadas**
5. Selecione **Redefinir** e **redefinir** novamente
6. Reinicie seu Surface Hub
