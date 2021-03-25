---
title: Gerenciar a configuração do Microsoft Teams no Surface Hub
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
localization_priority: Normal
description: Gerenciar configurações do Microsoft Teams no Surface Hub usando o Microsoft Intune e o Designer de Configuração do Windows
ms.openlocfilehash: 9c16fa4875febd3c9e0a8457626db5e09bf90545
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117379"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gerenciar configurações do Microsoft Teams no Surface Hub

Você pode gerenciar as configurações do Microsoft Teams em um Surface Hub usando o Designer de Configuração do Windows ou o Microsoft Intune no Microsoft Endpoint Manager. O conhecimento do Designer de Configuração do Windows ou do Microsoft Intune é necessário para fazer alterações nas configurações do Teams. Para obter mais informações sobre essas opções, consulte os seguintes artigos:

- [Criar um pacote de provisionamento para Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [O que é o gerenciamento de dispositivos do Microsoft Intune?](/mem/intune/remote-actions/device-management)

O Designer de Configuração do Windows é uma boa opção se você tiver apenas alguns dispositivos Surface Hub e você puder acessá-los facilmente. Se você tiver muitos Surface Hubs ou se eles estão em locais remotos, use o Microsoft Intune no Microsoft Endpoint Manager se estiver implantado em sua organização. Independentemente do método escolhido, você precisa criar um arquivo de configuração XML para fazer alterações nas configurações do Teams no Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintaxe de arquivo de configuração do Teams

A configuração do Teams em um Surface Hub é definida usando um arquivo XML. O arquivo XML contém todas as configurações que podem ser usadas para controlar como o Teams funciona. O Designer de Configuração do Windows e o Microsoft Intune usam a mesma sintaxe XML. Veja um exemplo do arquivo XML de configuração do Teams:

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
| Nenhum                    | `<SurfaceHubSettings>`                    |           | Contém todos os elementos de configuração para a configuração do Teams em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se o Surface Hub anuncia que ele está disponível para Bluetooth conexões.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se o Teams aceitará automaticamente reuniões baseadas em proximidade.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contém todos os elementos de configuração para Reuniões Coordenadas.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se o Teams está configurado para participar de Reuniões Coordenadas com outros dispositivos.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Esta é uma lista separada por vírgulas de UPNs para cada dispositivo da Sala do Teams ou Surface Hub do qual o dispositivo deve aceitar solicitações de junção de reunião ou para quais solicitações de junção de reunião devem ser enviadas.<br>Valores aceitos: cadeia de caracteres                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contém elementos de configuração de áudio e vídeo para reuniões coordenadas                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controla a configuração de áudio do Teams em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina em qual dispositivo o microfone estará ativo quando uma reunião for iniciada. Somente um dispositivo (normalmente um dispositivo salas do Teams) pode ter esse campo definido como enquanto o restante dos dispositivos deve ter esse campo definido para evitar eco de áudio e `true` `false` comentários.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se os participantes de uma reunião podem alternar ou desligar o microfone. Dispositivos nos quais **o padrão** de áudio é definido devem ter essa configuração definida para que os participantes não possam ativar acidentalmente um microfone e causar eco de áudio `false` ou `false` comentários.<p>Se **o padrão de** áudio estiver definido como , essa configuração será ignorada e os participantes poderão `true` silenciar ou desativar o microfone.<br>Valores aceitos: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controla a configuração de vídeo do Teams em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina em qual dispositivo a câmera estará ativa quando uma reunião for iniciada. Para a melhor experiência, recomendamos que apenas o dispositivo Salas do Teams seja definido como enquanto todos os outros `true` dispositivos estão definidos como `false` .<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se os participantes de uma reunião podem alternar ou desligar a câmera. Você pode definir isso como em qualquer outro dispositivo no evento que os participantes quiserem compartilhar diferentes perspectivas de vídeo (como se um participante estiver usando o quadro de comunicação `true` do Surface Hub). Se você não quiser que os participantes a liguem ou desliguem uma câmera em um dispositivo, de definir isso como `false` .<p> Se **o padrão de** vídeo estiver definido como , essa configuração será ignorada e os participantes poderão ativar ou desativar a `true` câmera.<br>Valores aceitos: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Aplicar configurações do Teams ao Surface Hub

Aplique ou atualize as configurações do Teams no Surface Hub usando o Designer de Configuração do Windows ou o Microsoft Intune no Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usar o Designer de Configuração do Windows

Você pode usar o Designer de Configuração do Windows para criar um pacote de provisionamento que pode ser usado para aplicar as configurações do Teams aos Surface Hubs. Você colará o arquivo XML criado acima no Designer de Configuração do Windows para criar o pacote de provisionamento.

> [!IMPORTANT]
> Se você já aplicou a configuração do Teams ao Surface Hub usando um pacote de provisionamento e deseja alterá-lo, você precisa remover o pacote de provisionamento existente primeiro. Para obter mais informações, [consulte Remove a provisioning package created by Windows Configuration Designer](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Faça o seguinte para criar o pacote de provisionamento no Designer de Configuração do Windows:

1. Instalar o Designer de Configuração do Windows na Windows Store no computador local e abri-lo
2. Selecione **Provisionar dispositivos Surface Hub** e **alternar para editor avançado**
3. Na próxima tela, **expanda o WindowsTeamSettings**  >  **Teams** e selecione **Configurações**
4. No campo ao lado **de Configurações** no painel intermediário, colar a única linha de XML que você criou acima
5. Selecione **Exportar**  >  **pacote de provisionamento**
6. Forneça um nome para o pacote de provisionamento em **Nome** e selecione **Next**  >  **Next**
7. Especifique um local para salvar o pacote de provisionamento e selecione **Next**
8. Selecione **Criar** para criar o pacote de provisionamento e, em seguida, **Concluir**

Por fim, depois de criar o pacote de provisionamento, faça o seguinte para aplicar o pacote de provisionamento ao Surface Hub:

1. Salve o pacote de provisionamento criado acima em uma unidade USB
2. Inserir a unidade USB em seu Surface Hub
3. No Surface Hub, abra o menu Iniciar, selecione **Todos os aplicativos** e selecione **Configurações**
4. Forneça seu nome de usuário e senha do administrador e selecione **Sim**
5. Vá para **o Surface Hub,** **Gerenciamento de dispositivos,** Adicionar ou remover um pacote **de provisionamento** e adicionar **um pacote**
6. Em **Selecionar um pacote,** selecione **Adicionar** ao lado do pacote de provisionamento e reinicie o Surface Hub

### <a name="use-microsoft-intune"></a>Usar o Microsoft Intune

Se os Surface Hubs são gerenciados usando o Microsoft Intune no Microsoft Endpoint Management, você pode usá-lo para aplicar as configurações do Teams aos surface hubs. Você criará um novo perfil de configuração e colará o arquivo XML criado acima nele.

> [!IMPORTANT]
> Os Surface Hubs precisam estar em um grupo de dispositivos para que o Microsoft Intune possa identificar a quais dispositivos aplicar o perfil de configuração. Para obter informações sobre como criar um grupo de dispositivos, consulte [Adicionar grupos para organizar usuários e dispositivos.](/mem/intune/fundamentals/groups-add)

Faça o seguinte para criar um perfil de configuração para aplicar as configurações do Teams aos Surface Hubs:

1. Entre no Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Navegue até **Perfis**  >  **de Configuração de Dispositivos** e selecione **Criar perfil**
3. Em **Plataforma**, selecione **Windows 10 e posterior**
4. Em **Perfil,** selecione **Personalizado** e clique em **Criar**
5. Na guia **Noções Básicas,** em **Nome**, forneça um nome descritivo para seu perfil de configuração e selecione **Next**
6. Na guia **Configuração,** selecione **Adicionar**
7. No painel **Adicionar** linha, faça o seguinte:
    1. Forneça um nome descritivo e, opcionalmente, uma descrição da configuração do Teams que você está adicionando
    2. No **OMA-URI,** insira `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Em **Tipo de dados,** selecione **Cadeia de caracteres (arquivo XML)**
    4. Abra o navegador de arquivos, selecione o arquivo XML criado acima e **Abra**
8. Selecione **Adicionar** e, em **seguida, Próximo**
9. Na guia **Atribuições,** certifique-se de **atribuir está** definido como **Grupos Selecionados**
10. Em **Grupos Selecionados**, selecione **Selecionar grupos** para incluir e escolher o grupo que contém seus Surface Hubs e selecione **Selecionar**
11. Selecione **Próximo**, **Próximo**
12. Na revisão **+ criar,** selecione **Criar**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Remover configurações do Teams de um Surface Hub

Remova as configurações do Teams no Surface Hub usando o Designer de Configuração do Windows ou o Microsoft Intune no Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Remover um pacote de provisionamento criado pelo Designer de Configuração do Windows

Se você aplicou as configurações do Teams a um Surface Hub usando um pacote de provisionamento criado pelo Designer de Configuração do Windows, use as etapas a seguir para remover o pacote e suas configurações:

1. No Surface Hub, abra o menu Iniciar, selecione **Todos os aplicativos** e selecione **Configurações**
2. Forneça seu nome de usuário e senha do administrador e selecione **Sim**
3. Vá para **o Surface Hub,** **gerenciamento de dispositivos** **e adicione ou remova um pacote de provisionamento**
4. Ao lado do pacote de provisionamento que você deseja remover, selecione **Remover**
5. Vá para **o Surface Hub** e, em seguida, **aplicativos & recursos**
6. Encontre **o Microsoft Teams para o Surface Hub** e selecione Opções **Avançadas**
7. Selecione **Redefinir** e **redefinir** novamente
8. Reinicie o Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Remover configurações aplicadas pelo Microsoft Intune

Se você aplicou as configurações do Teams a um Surface Hub usando o Microsoft Intune no Gerenciamento de Pontos de Extremidade da Microsoft, use as etapas a seguir para remover o perfil de configuração e suas configurações:

1. Entre no Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Navegar até **perfis de**  >  **configuração de dispositivos**
3. Selecione o perfil de configuração que contém as configurações de Reunião Coordenadas que você deseja remover
4. Na página detalhes do perfil de configuração, selecione **Excluir** **e,** em seguida, OK

Depois de remover o perfil de configuração que continha as configurações de Reunião Coordenadas do Surface Hub, use as etapas a seguir para redefinir o aplicativo do Teams no Surface Hub:

1. No Surface Hub, abra o menu Iniciar, selecione **Todos os aplicativos** e selecione **Configurações**
2. Forneça seu nome de usuário e senha do administrador e selecione **Sim**
3. Vá para **o Surface Hub** e, em seguida, **aplicativos & recursos**
4. Encontre **o Microsoft Teams para o Surface Hub** e selecione Opções **Avançadas**
5. Selecione **Redefinir** e **redefinir** novamente
6. Reinicie o Surface Hub