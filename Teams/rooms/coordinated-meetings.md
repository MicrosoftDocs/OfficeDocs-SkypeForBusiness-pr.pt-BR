---
title: Configurar reuniões coordenadas com salas e Surface Hub do Microsoft Teams
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
description: Configurar dispositivos de salas de equipe e o Surface Hub para ingressar em reuniões quando um dispositivo ou o outro ingressar em uma reunião.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803933"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar reuniões coordenadas com salas e Surface Hub do Microsoft Teams

Se você tiver um ou mais dispositivos de salas do Microsoft Teams ou Surface Hub em uma sala de reunião, poderá configurar reuniões coordenadas. Reuniões coordenadas permite que você configure seus dispositivos de salas de equipe e hubs de superfície para que, ao ingressar em uma reunião em um dispositivo, os outros dispositivos da sala também sejam associados à mesma reunião. Você pode configurar câmeras, alto-falantes e microfones para que aqueles que dão aos participantes a melhor experiência sejam habilitados enquanto outras pessoas estiverem desabilitadas. Isso evita que os participantes de ruído de Dreaded eco e comentários possam ocorrer ao adicionar vários dispositivos a uma reunião.

Para configurar reuniões coordenadas, você precisa garantir que seus dispositivos de sala de equipe e hubs de superfície já estejam configurados corretamente para participar de reuniões. O mais importante é que cada dispositivo precisa ter sua própria caixa de correio de sala do Exchange. Para obter informações sobre como configurá-los, consulte os seguintes artigos:

- [Implantar Salas do Microsoft Teams](../rooms/rooms-deploy.md)
- [Criar uma conta de dispositivo do Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Depois de confirmar que seus dispositivos de salas de equipe e hubs de superfície podem aceitar automaticamente reuniões e ingressar com êxito, você pode configurar reuniões coordenadas.

As etapas a seguir devem ser concluídas para cada sala de reunião separadamente. Os dispositivos em uma sala de reunião não devem ser configurados para reuniões coordenadas com dispositivos em outras salas de reunião.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Etapa 1: planejar sua experiência de reunião coordenada

Antes de fazer alterações de configuração, você precisa decidir quais dispositivos farão isso em cada sala de reunião. Ou seja, para uma determinada sala de reuniões, você precisa decidir qual dispositivo terá o microfone, câmera e quadro de comunicações ativos. A maneira como você configura seus dispositivos depende do seu ambiente específico, mas aqui estão algumas recomendações gerais para começar:

- **Microfone** Dispositivo de salas de equipe
- Da **câmera** Dispositivo de salas de equipe (ativado por padrão) e Surface Hub (desativado por padrão, mas que podem ser ativados pelos participantes)
- **Quadro de comunicações** Surface Hub

> [!IMPORTANT]
> Verifique se você habilitou o microfone apenas em um dispositivo. Se você ativá-la em mais de um dispositivo, terá eco e retorno de áudio.

## <a name="step-2-get-your-devices-upns"></a>Etapa 2: obter os UPNs dos seus dispositivos

Ao configurar uma experiência de reunião coordenada em uma sala de reunião, você precisa dizer aos dispositivos de salas de equipe e hubs de superfície na sala em que os dispositivos se coordenam. Isso é feito por meio da adição do nome UPN dos dispositivos que ele deve coordenar com sua configuração. Se não souber os UPNs para cada um dos dispositivos que deseja configurar para as reuniões coordenadas, você poderá encontrá-los usando o centro de administração do Microsoft 365. 

Você precisa ser atribuído a uma função de administrador para acessar o centro de administração do Microsoft 365. Para obter mais informações, consulte [sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

Para obter os UPNs de seus dispositivos de salas de equipe e hubs de superfície, faça o seguinte:

1. Acesse o centro de administração do Microsoft 365 visitando https://admin.microsoft.com .
2. Vá para usuários ativos do **usuário**  >  **Active users**.
3. Localize o nome do dispositivo de salas de equipe ou do Surface Hub na coluna **nome para exibição** (você pode usar a caixa de **pesquisa** se tiver muitos usuários).
4. Localize o UPN na coluna **username** (parecerá algo parecido com alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Repita este procedimento para cada dispositivo que participará de reuniões coordenadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Etapa 3: criar uma planilha de implantação

Depois de planejar a sua experiência de reunião coordenada e reunir uma lista dos UPNs dos seus dispositivos, é uma boa ideia criar uma planilha de implantação. Uma planilha de implantação vai ajudá-lo a visualizar a configuração que você deseja definir em todos os seus dispositivos, permitindo que você valide suas opções e verifique se há erros.

Em um aplicativo de planilha, adicione linhas para o seguinte na primeira coluna:

| Configuração                | Descrição      |
|------------------------|-----------------|
| **Áudio padrão**      | Determina em qual dispositivo o microfone estará ativo quando uma reunião iniciar. Somente um dispositivo (geralmente um dispositivo de salas de equipe) pode ter esse campo definido como `true` enquanto o restante dos dispositivos deve ter esse campo definido para `false` evitar eco e retorno de áudio.          |
| **Áudio habilitado**      | Determina se os participantes de uma reunião podem ligar ou desligar o microfone. Os dispositivos nos quais o **áudio padrão** está definido `false` devem ter essa configuração definida como para `false` que os participantes não possam ligar acidentalmente um microfone e causar eco de áudio ou comentários.<p>Se o **padrão de áudio** estiver definido como `true` , essa configuração será ignorada e os participantes poderão ativar ou desativar o mudo do microfone.          |
| **Vídeo padrão**      | Determina em qual dispositivo a câmera estará ativa quando uma reunião iniciar. Para obter a melhor experiência, recomendamos que apenas o dispositivo de salas de equipe seja definido `true` enquanto todos os outros dispositivos são definidos como `false` .          |
| **Vídeo habilitado**      | Determina se os participantes de uma reunião podem ativar ou desativar a câmera. Você pode definir isso como `true` em qualquer outro dispositivo nos participantes do evento querem compartilhar perspectivas de vídeo diferentes (como se um participante usar o quadro de comunicações do Surface Hub). Se você não quiser que os participantes ativem ou desativem uma câmera em um dispositivo, defina-o como `false` .<p> Se o **padrão de vídeo** estiver definido como `true` , essa configuração será ignorada e os participantes poderão ativar ou desativar a câmera.         |
| **Quadro de comunicações padrão** | Determina se o dispositivo de salas de equipe exibirá um quadro de comunicações compartilhado por um dos participantes da reunião. Recomendamos que você o defina para `false` se tiver um Surface Hub e `true` se não tiver um. Essa configuração não tem efeito em hubs de superfície. Os hubs de Surface sempre exibirão um quadro de comunicações compartilhado por participantes da reunião.         |
| **Quadro de comunicações habilitado** | Determina se os participantes de uma reunião podem ativar ou desativar o quadro de comunicações. Se você não quiser que os participantes ativem ou desativem o quadro de comunicações em um dispositivo, defina-o como `false` . <p>Se o **padrão do quadro de comunicações** estiver definido como `true` , essa configuração será ignorada e os participantes poderão ativar ou desativar o quadro de comunicações.
| **Contas confiáveis**   | Esta é uma lista separada por vírgulas de UPNs para cada dispositivo de sala de equipes ou Surface Hub para o qual o dispositivo deve aceitar solicitações de junção de reunião ou para as quais as solicitações de ingresso em reunião devem ser enviadas. |

Em colunas subsequentes, adicione cada um dos dispositivos de sala de equipe e hubs de superfície. Em cada coluna, preencha os valores que correspondem à experiência que você deseja para a sala de reunião. Veja um exemplo com um dispositivo de salas de equipe e um Surface Hub:

- Dispositivo de equipe
  - O áudio e o vídeo **são ativados quando uma** reunião é iniciada. Os participantes **podem** ativar ou desativar o áudio e o vídeo.
  - A exibição de um quadro de comunicações compartilhado está desativada.
- Surface Hub
  - O áudio é **desativado** quando uma reunião é iniciada. Os participantes **não podem** ativar ou desativar o áudio.
  - O vídeo está **desativado** quando uma reunião é iniciada. Os participantes **podem** ligar ou desligar o vídeo.

| Configuração                | Sala de equipes      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Áudio padrão**      | `true`          | `false`          |
| **Áudio habilitado**      | `true`          | `false`          |
| **Vídeo padrão**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Quadro de comunicações padrão** | `false`         | `false`          |
| **Contas confiáveis**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Etapa 4: configurar o dispositivo de salas de equipe

Você pode configurar reuniões coordenadas em um dispositivo de salas de equipe usando a tela sensível ao toque do dispositivo ou, se precisar configurar muitos dispositivos e desejar fazer isso em um local central, poderá usar um arquivo de configuração XML.

Use a planilha que você criou na etapa anterior para ajudá-lo a configurar seus dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Use a tela sensível ao toque do dispositivo de salas de equipe

Para configurar reuniões coordenadas em um dispositivo, faça o seguinte:

1. Selecionar **... Mais**  >  **configurações**.
2. Digite a senha do administrador e selecione **Sim**.
3. Selecione **reuniões coordenadas**.
4. Em **Opções**, defina **reunião coordenada** como _ativada_.
5. Se o **áudio padrão** for a sua planilha `true` , defina a **opção ativar o microfone do dispositivo** como ativado; caso contrário, deixe-o _desligado_.
6. Se o **áudio estiver habilitado** na planilha `true` , selecione **permitir que as pessoas habilitem ao ingressar em uma reunião** em **ativar o microfone do dispositivo**. Esta opção não poderá ser desativada se a opção **ativar o microfone do dispositivo** estiver definida como ativado.
7. Se a opção **padrão vídeo** estiver em sua planilha `true` , defina **ativar a câmera do dispositivo** para ligado; caso contrário, deixe-a como _desativada_.
8. Se o **vídeo habilitado** na planilha for `true` , selecione **permitir que as pessoas habilitem ao ingressar em uma reunião** em **ativar a câmera do dispositivo**. Essa opção não pode ser desativada se a **câmera do dispositivo** estiver definida como _ativado_.
9. Se o recurso de **quadro de comunicações for padrão** em sua planilha `true` , defina **ativar o quadro de comunicações neste dispositivo** como _ativado_, caso contrário, deixe-o _desligado_.
10. Em **contas de dispositivos confiáveis**, digite cada UPN listado em **contas confiáveis** na planilha. Separe vários UPNs com vírgulas.
11. Selecione **salvar e sair**.

Depois que você selecionar **salvar e sair**, o dispositivo será reiniciado e ele estará pronto para participar de reuniões coordenadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar o arquivo de configuração XML de salas de equipe

Reuniões coordenadas podem ser configuradas usando o arquivo de configuração XML do dispositivo de salas de equipe `SkypeSettings.xml` . O `SkypeSettings.xml` arquivo não é um arquivo estático. Quando o dispositivo de salas de equipe iniciar, ele faz check-in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` para um arquivo nomeado `SkypeSettings.xml` . Se o arquivo existir, o dispositivo lerá e aplicará a configuração especificada no arquivo. Após concluir a aplicação da configuração, o arquivo é excluído. Para obter mais informações sobre o `SkypeSettings.xml` arquivo, consulte [gerenciar configurações de console com um arquivo de configuração XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Veja a seguir a sintaxe das configurações de reuniões coordenadas no arquivo de configuração:

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

Para configurar reuniões coordenadas em um dispositivo, faça o seguinte:

1. Em um editor de arquivo de texto, como o código do Visual Studio ou o bloco de notas, Cole o XML acima em um novo arquivo.

2. Defina cada um dos elementos XML para o `true` valor correspondente ou `false` na planilha. Por exemplo, se o **padrão de áudio** for `true` definido `<Audio default="true">` .

3. Certifique-se de mudar `TrustedAccounts` para sua lista de UPNs.

4. Salve o arquivo com o nome `SkypeSettings.xml` .

5. Coloque o arquivo na pasta do dispositivo de salas de equipe `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Você pode fazer isso de algumas maneiras:

    - **Copiar o arquivo para o dispositivo de salas de equipe** Você precisará habilitar o compartilhamento de arquivos e criar um compartilhamento de rede antes de poder copiar arquivos para o seu dispositivo. Depois de fazer isso, você pode se conectar ao compartilhamento de rede e copiar o arquivo para o dispositivo. Para obter mais informações, consulte [manutenção e operações de salas do Microsoft Teams](../rooms/rooms-operations.md).
    - **Usar uma política de grupo** Crie uma política de grupo para copiar o arquivo para o dispositivo. Para obter mais informações, consulte [visão geral da política de grupo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Baixar o arquivo no dispositivo salas de equipe** Você pode conectar-se ao dispositivo usando o modo de administração e, em seguida, copiar o arquivo para o dispositivo a partir de um compartilhamento de rede ou unidade USB. Para obter mais informações, consulte [alternando para o modo de administrador](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Reinicie o dispositivo. Você pode fazer isso de duas maneiras:

    - **PowerShell remoto** Você pode executar o comando shutdown no dispositivo usando o PowerShell remoto. Para obter mais informações, consulte [gerenciamento remoto usando o PowerShell](../rooms/rooms-operations.md).
    - **Executar reinicialização-computador** Você pode executar o `Restart-Computer` cmdlet em seu computador local e especificar o nome do computador do dispositivo que você deseja reiniciar. Para obter mais informações, consulte [Restart-Computer](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Etapa 5: configurar o Surface Hub

Você pode usar o designer de configuração do Windows para criar um pacote de provisionamento que você pode usar para aplicar as configurações de coordenação de reuniões a seus hubs Surface. Você colará o arquivo XML criado acima no designer de configuração do Windows para criar o pacote de provisionamento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Criar arquivo de configuração XML de reuniões coordenadas para o Surface Hub

O designer de configuração do Windows e o Microsoft Intune são usados para aplicar a configuração de reuniões coordenadas aos hubs de superfície. A configuração é definida usando XML. Antes de prosseguir, você precisa criar o XML que será aplicado.

Veja a seguir a sintaxe do arquivo de configuração XML das reuniões coordenadas.

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

Siga este procedimento para preparar o designer de configuração do XML para Windows ou do Microsoft Intune:

1. Em um editor de arquivo de texto, como o código do Visual Studio ou o bloco de notas, Cole o XML acima em um novo arquivo.

2. Defina cada um dos elementos XML para o `true` valor correspondente ou `false` na planilha. Por exemplo, se o **padrão de áudio** for `true` definido `<Audio default="true">` .

3. Certifique-se de mudar `TrustedAccounts` para sua lista de UPNs.

4. O designer de configuração do Windows exige que o XML esteja em uma única linha. Remova todas as quebras de linha entre cada linha, de modo que o XML tenha a aparência da seguinte forma:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salve o arquivo no seu computador.

Depois de criar o arquivo de configuração XML, use as etapas em [gerenciar as configurações do Microsoft Teams no Surface Hub](surface-hub-manage-config.md) para aplicá-la aos hubs Surface.
