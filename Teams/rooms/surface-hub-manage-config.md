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
description: Gerenciar as configurações do Microsoft Teams no Surface Hub usando o Microsoft Intune e o designer de configuração do Windows
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761424"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gerenciar as configurações do Microsoft Teams no Surface Hub

Você pode gerenciar as configurações do Microsoft Teams em um Surface Hub usando o designer de configuração do Windows ou o Microsoft Intune no Microsoft Endpoint Manager. O conhecimento do designer de configuração do Windows ou do Microsoft Intune é necessário para fazer alterações nas configurações do teams. Para obter mais informações sobre essas opções, consulte os seguintes artigos:

- [Criar um pacote de provisionamento para Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [O que é o gerenciamento de dispositivos do Microsoft Intune?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

O designer de configuração do Windows é uma boa opção se você tiver apenas alguns dispositivos Surface Hub e poderá acessá-los facilmente. Se você tiver muitos hubs de Surface ou se eles estiverem em locais remotos, use o Microsoft Intune no Microsoft Endpoint Manager, caso ele tenha sido implantado em sua organização. Independentemente do método escolhido, você precisará criar um arquivo de configuração XML para fazer alterações nas configurações do teams no Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintaxe do arquivo de configuração do teams

A configuração do teams em um Surface Hub é definida usando um arquivo XML. O arquivo XML contém todas as configurações que podem ser usadas para controlar a forma como o Microsoft Teams funciona. O designer de configuração do Windows e o Microsoft Intune usam a mesma sintaxe XML. Veja um exemplo do arquivo XML de configuração do teams:

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

A tabela a seguir descreve todas as definições de configuração disponíveis no arquivo de configuração:

| Mãe                  | Elemento                                   | Atributo | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nenhum                    | `<SurfaceHubSettings>`                    |           | Contém todos os elementos de configuração para a configuração do teams em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se o Surface Hub anuncia que ele está disponível para conexões Bluetooth.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se as equipes aceitarão automaticamente reuniões com base em proximidade.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contém todos os elementos de configuração para reuniões coordenadas.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se o Microsoft Teams está configurado para participar de reuniões coordenadas com outros dispositivos.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Esta é uma lista separada por vírgulas de UPNs para cada dispositivo de sala de equipes ou Surface Hub para o qual o dispositivo deve aceitar solicitações de junção de reunião ou para as quais as solicitações de ingresso em reunião devem ser enviadas.<br>Valores aceitos: cadeia de caracteres                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contém elementos de configuração de áudio e vídeo para reuniões coordenadas                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controla a configuração de áudio para equipes em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina em qual dispositivo o microfone estará ativo quando uma reunião iniciar. Somente um dispositivo (geralmente um dispositivo de salas de equipe) pode ter esse campo definido como `true` enquanto o restante dos dispositivos deve ter esse campo definido para `false` evitar eco e retorno de áudio.<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se os participantes de uma reunião podem ligar ou desligar o microfone. Os dispositivos nos quais o **áudio padrão** está definido `false` devem ter essa configuração definida como para `false` que os participantes não possam ligar acidentalmente um microfone e causar eco de áudio ou comentários.<p>Se o **padrão de áudio** estiver definido como `true` , essa configuração será ignorada e os participantes poderão ativar ou desativar o mudo do microfone.<br>Valores aceitos: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controla a configuração de vídeo para equipes em um Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina em qual dispositivo a câmera estará ativa quando uma reunião iniciar. Para obter a melhor experiência, recomendamos que apenas o dispositivo de salas de equipe seja definido `true` enquanto todos os outros dispositivos são definidos como `false` .<br>Valores aceitos: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se os participantes de uma reunião podem ativar ou desativar a câmera. Você pode definir isso como `true` em qualquer outro dispositivo nos participantes do evento querem compartilhar perspectivas de vídeo diferentes (como se um participante usar o quadro de comunicações do Surface Hub). Se você não quiser que os participantes ativem ou desativem uma câmera em um dispositivo, defina-o como `false` .<p> Se o **padrão de vídeo** estiver definido como `true` , essa configuração será ignorada e os participantes poderão ativar ou desativar a câmera.<br>Valores aceitos: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Aplicar configurações de equipe ao Surface Hub

Aplique ou atualize as configurações do teams no Surface Hub usando o Windows Configuration designer ou o Microsoft Intune no Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usar o designer de configuração do Windows

Você pode usar o designer de configuração do Windows para criar um pacote de provisionamento que você pode usar para aplicar as configurações do Team em seus hubs Surface. Você colará o arquivo XML criado acima no designer de configuração do Windows para criar o pacote de provisionamento.

> [!IMPORTANT]
> Se você já aplicou a configuração do Microsoft Teams ao seu Surface Hub usando um pacote de provisionamento e deseja alterá-lo, será necessário remover primeiro o pacote de provisionamento existente. Para obter mais informações, consulte [remover um pacote de provisionamento criado pelo designer de configuração do Windows](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Faça o seguinte para criar o pacote de provisionamento no designer de configuração do Windows:

1. Instalar o designer de configuração do Windows na Windows Store em seu computador local e abri-lo
2. Selecione **provisionar dispositivos Surface Hub** e, em seguida, **alternar para o editor avançado**
3. Na tela seguinte, expanda **WindowsTeamSettings**  >  **Teams** WindowsTeamSettings e selecione **configurações**
4. No campo ao lado de **configurações** no painel do meio, Cole a única linha do XML que você criou acima
5. Selecionar **Export**  >  **pacote de provisionamento** de exportação
6. Forneça um nome para o pacote de provisionamento em **nome** e selecione **próximo**  >  **próximo**
7. Especifique um local para salvar o pacote de provisionamento e selecione **Avançar**
8. Selecione **Compilar** para criar o pacote de provisionamento e, em seguida, **concluir**

Por fim, depois de criar o pacote de provisionamento, siga este procedimento para aplicar o pacote de provisionamento ao seu Surface Hub:

1. Salvar o pacote de provisionamento que você criou acima em uma unidade USB
2. Insira a unidade USB no seu Surface Hub
3. No Surface Hub, abra o menu Iniciar, selecione **todos os aplicativos**e, em seguida, selecione **configurações**
4. Forneça o nome de usuário e a senha do administrador e, em seguida, selecione **Sim**
5. Vá para **Surface Hub**, **Gerenciamento de dispositivo**, **adicione ou remova um pacote de provisionamento**e, em seguida, **adicione um pacote**
6. Em **selecionar um pacote**, selecione **Adicionar** ao lado do pacote de provisionamento e reinicie o Surface Hub

### <a name="use-microsoft-intune"></a>Usar o Microsoft Intune

Se seus hubs de Surface forem gerenciados usando o Microsoft Intune no Microsoft Endpoint Management, você poderá usá-lo para aplicar configurações de equipe aos hubs Surface. Você criará um novo perfil de configuração e, em seguida, colará o arquivo XML criado acima nele.

> [!IMPORTANT]
> Seus hubs de superfície precisam estar em um grupo de dispositivos para que o Microsoft Intune possa identificar para quais dispositivos aplicar o perfil de configuração. Para obter informações sobre como criar um grupo de dispositivos, consulte [Adicionar grupos para organizar usuários e dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

Siga este procedimento para criar um perfil de configuração para aplicar as configurações do teams a seus hubs de superfície:

1. Acesse o Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Navegar para **Devices**  >  **perfis de configuração** de dispositivos e selecionar **Criar perfil**
3. Em **plataforma**, selecione **Windows 10 e posterior**
4. Em **perfil**, selecione **personalizado**e, em seguida, clique em **criar**
5. Na guia **noções básicas** , em **nome**, forneça um nome descritivo para seu perfil de configuração e selecione **Avançar**
6. Na guia **configurações de configuração** , selecione **Adicionar**
7. No painel **Adicionar linha** , faça o seguinte:
    1. Forneça um nome descritivo e, opcionalmente, uma descrição da configuração do teams que você está adicionando
    2. Em **OMA-URI**, digite `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Em **tipo de dados**, selecione **cadeia de caracteres (arquivo XML)**
    4. Abra o navegador de arquivos, selecione o arquivo XML que você criou acima e **abra**
8. Selecione **Adicionar** e, em seguida, **Avançar**
9. Na guia **tarefas** , certifique-se de que **atribuir a** está definido como **grupos selecionados**
10. Em **grupos selecionados**, selecione **Selecionar grupos para incluir** e escolha o grupo que contém os hubs de superfície e selecione **selecionar**
11. Selecionar **próximo**, **próximo**
12. Na guia **revisar + criar**, selecione **criar**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Remover as configurações do teams de um Surface Hub

Remova as configurações do teams no Surface Hub usando o Windows Configuration designer ou o Microsoft Intune no Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Remover um pacote de provisionamento criado pelo designer de configuração do Windows

Se você aplicou configurações do teams a um Surface Hub usando um pacote de provisionamento criado pelo Windows Configuration designer, use as etapas a seguir para remover o pacote e suas configurações:

1. No Surface Hub, abra o menu Iniciar, selecione **todos os aplicativos**e, em seguida, selecione **configurações**
2. Forneça o nome de usuário e a senha do administrador e, em seguida, selecione **Sim**
3. Vá para **Surface Hub**, **Gerenciamento de dispositivo** e, em seguida, **Adicionar ou remover um pacote de provisionamento**
4. Ao lado do pacote de provisionamento que você deseja remover, selecione **remover**
5. Vá para o **Surface Hub** e, em seguida, **aplicativos & recursos**
6. Encontre **o Microsoft Teams para Surface Hub** e selecione **Opções avançadas**
7. Selecione **Redefinir**e **Redefinir** novamente
8. Reiniciar o Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Remover as configurações aplicadas pelo Microsoft Intune

Se você aplicou configurações do teams a um Surface Hub usando o Microsoft Intune no Microsoft Endpoint Management, use as etapas a seguir para remover o perfil de configuração e suas configurações:

1. Acesse o Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Navegar para **Devices**  >  **perfis de configuração** de dispositivos
3. Selecione o perfil de configuração que contém as configurações de reunião coordenada que você deseja remover
4. Na página detalhes do perfil de configuração, selecione **excluir** e **OK**

Depois de remover o perfil de configuração que continha as configurações de reunião coordenada para seu Surface Hub, use as etapas a seguir para redefinir o aplicativo Teams no Surface Hub:

1. No Surface Hub, abra o menu Iniciar, selecione **todos os aplicativos**e, em seguida, selecione **configurações**
2. Forneça o nome de usuário e a senha do administrador e, em seguida, selecione **Sim**
3. Vá para o **Surface Hub** e, em seguida, **aplicativos & recursos**
4. Encontre **o Microsoft Teams para Surface Hub** e selecione **Opções avançadas**
5. Selecione **Redefinir**e **Redefinir** novamente
6. Reiniciar o Surface Hub