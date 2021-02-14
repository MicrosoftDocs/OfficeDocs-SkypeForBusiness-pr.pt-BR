---
title: Configurar reuniões coordenadas com salas do Microsoft Teams e Surface Hub
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
description: Configure os dispositivos salas do Teams e o Surface Hub para ingressar em reuniões quando um dispositivo ou outro ingressar em uma reunião.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803933"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar Reuniões Coordenadas com salas do Microsoft Teams e Surface Hub

Se você tiver um ou mais dispositivos de Salas do Microsoft Teams ou Surface Hubs em uma sala de reunião, poderá configurar Reuniões Coordenadas. As Reuniões Coordenadas permitem configurar seus dispositivos de Salas do Teams e Surface Hubs para que, ao ingressar em uma reunião em um dispositivo, os outros dispositivos na sala também sejam ingressados na mesma reunião. Você pode configurar suas câmeras, alto-falantes e microfones para que aqueles que dão aos participantes a melhor experiência sejam habilitados enquanto outras pessoas estão desabilitadas. Isso evita o eco e o ruído de comentários que os participantes podem experimentar ao adicionar vários dispositivos a uma reunião.

Para configurar Reuniões Coordenadas, você precisa garantir que seus dispositivos de Salas do Teams e Surface Hubs já estão configurados corretamente para participar de reuniões. O mais importante é que cada dispositivo precise ter sua própria caixa de correio da sala do Exchange. Para obter informações sobre como configurar, consulte os seguintes artigos:

- [Implantar Salas do Microsoft Teams](../rooms/rooms-deploy.md)
- [Criar conta de dispositivo do Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Depois de confirmar que seus dispositivos de Salas do Teams e Surface Hubs podem aceitar reuniões automaticamente e ingressar com êxito, você pode configurar Reuniões Coordenadas.

As etapas a seguir devem ser concluídas para cada sala de reunião separadamente. Os dispositivos em uma sala de reunião não devem ser definidos para Reuniões Coordenadas com dispositivos em outras salas de reunião.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Etapa 1: Planejar sua experiência de Reunião Coordenada

Antes de fazer alterações de configuração, você precisa decidir quais dispositivos fazerão o que em cada sala de reunião. Ou seja, para uma determinada sala de reunião, você precisa decidir qual dispositivo terá o microfone, a câmera e o quadro de branco ativos. A forma como você configura seus dispositivos depende do seu ambiente específico, mas aqui estão algumas recomendações gerais para começar:

- **Microfone** Dispositivo Salas do Teams
- **Câmera** Dispositivo Salas do Teams (ligado por padrão) e Surface Hub (desligado por padrão, mas permitido para ser ligado pelos participantes)
- **Quadro de informações** Surface Hub

> [!IMPORTANT]
> Certifique-se de habilitar o microfone apenas em um dispositivo. Se você habilita-lo em mais de um dispositivo, você experimentará o eco de áudio e os comentários.

## <a name="step-2-get-your-devices-upns"></a>Etapa 2: Obter upns dos dispositivos

Ao configurar uma experiência de Reunião Coordenada em uma sala de reunião, você precisa dizer aos dispositivos de Salas do Teams e surface hubs nessa sala com quais dispositivos coordenar. Isso é feito adicionando o upn (nome principal de usuário) dos dispositivos com os que ele deve coordenar à sua configuração. Se você não conhece os UPNs de cada um dos dispositivos que deseja configurar para Reuniões Coordenadas, pode encontrá-los usando o Centro de administração do Microsoft 365. 

Você precisa ter uma função de administrador para acessar o Centro de administração do Microsoft 365. Para obter mais informações, consulte [Sobre as funções de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

Para obter os UPNs de seus dispositivos salas do Teams e surface hubs, faça o seguinte:

1. Entre no Centro de administração do Microsoft 365 https://admin.microsoft.com visitando.
2. Vá para **Usuários**  >  **Ativos.**
3. Encontre o nome do dispositivo Salas do  Teams ou do Surface  Hub na coluna Nome de exibição (você pode usar a caixa Pesquisar se tiver muitos usuários).
4. Encontre o UPN na **coluna** Nome de usuário (ele se parece com alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Repita esse processo para cada dispositivo que participará de Reuniões Coordenadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Etapa 3: criar uma planilha de implantação

Depois de planejar sua experiência de Reunião Coordenada e reunir uma lista dos UPNs de seus dispositivos, é uma boa ideia criar uma planilha de implantação. Uma planilha de implantação ajudará você a visualizar a configuração que você deseja definir em todos os seus dispositivos, permitindo validar suas escolhas e verificar se há erros.

Em um aplicativo de planilha, adicione linhas para o seguinte na primeira coluna:

| Configuração                | Descrição      |
|------------------------|-----------------|
| **Padrão de áudio**      | Determina em qual dispositivo o microfone estará ativo quando uma reunião for iniciada. Somente um dispositivo (normalmente um dispositivo salas do Teams) pode ter esse campo definido enquanto o restante dos dispositivos deve ter esse campo definido para evitar o eco de áudio `true` `false` e os comentários.          |
| **Áudio habilitado**      | Determina se os participantes de uma reunião podem alternar ou desligar o microfone. Os dispositivos **em** que o padrão de áudio está definido devem ter essa configuração definida para que os participantes não possam ativar acidentalmente um microfone e causar eco `false` de áudio ou `false` comentários.<p>Se **o padrão de** áudio estiver definido como, essa configuração será ignorada e os participantes poderão silenciar ou `true` desativar mudo do microfone.          |
| **Vídeo padrão**      | Determina em qual dispositivo a câmera estará ativa quando uma reunião for iniciada. Para ter a melhor experiência, recomendamos que somente o dispositivo Salas do Teams seja definido enquanto todos os outros `true` dispositivos estão definidos `false` como.          |
| **Vídeo habilitado**      | Determina se os participantes de uma reunião podem alternar ou desligar a câmera. Você pode definir isso como em qualquer outro dispositivo no evento em que os participantes do evento quiserem compartilhar perspectivas de vídeo diferentes (por exemplo, se um participante estiver usando o quadro de comunicação `true` do Surface Hub). Se você não quiser que os participantes a liguem ou desliguem uma câmera em um dispositivo, de definida como `false` .<p> Se **o padrão do** vídeo estiver definido `true` como, essa configuração será ignorada e os participantes poderão ligar ou desativar a câmera.         |
| **Whiteboard padrão** | Determina se o dispositivo Salas do Teams exibirá um quadro de branco compartilhado por um dos participantes da reunião. Recomendamos definir isso como se você tiver um Surface Hub e se `false` `true` não tiver um. Essa configuração não tem efeito nos Surface Hubs. Os Surface Hubs sempre exibirão um quadro de branco compartilhado pelos participantes da reunião.         |
| **Quadro de branco habilitado** | Determina se os participantes de uma reunião podem alternar ou não o quadro de branco. Se você não quiser que os participantes a liguem ou desliguem o quadro de whiteboard em um dispositivo, de defini-lo como `false` . <p>Se **o padrão do Whiteboard** estiver definido como, essa configuração será ignorada e os participantes poderão ativar ou desativar o quadro de `true` informações.
| **Contas confiáveis**   | Esta é uma lista separada por vírgula de UPNs para cada dispositivo da Sala do Teams ou Surface Hub a partir do qual o dispositivo deve aceitar solicitações de ingressar na reunião ou para quais solicitações de junção de reunião devem ser enviadas. |

Nas colunas subsequentes, adicione cada um dos seus dispositivos de Salas do Teams e Surface Hubs. Em cada coluna, preencha os valores que correspondem à experiência que você deseja para a sala de reunião. Veja um exemplo com um dispositivo salas do Teams e um Surface Hub:

- Dispositivo teams
  - O áudio e o vídeo são **acionados** quando uma reunião é iniciada. Os participantes **podem** alternar entre áudio e vídeo.
  - A exibição de um quadro de branco compartilhado está desligada.
- Surface Hub
  - O áudio é **desligado quando** uma reunião é iniciada. Os participantes **não podem alternar** o áudio ou desligar.
  - O vídeo é **desligado quando** uma reunião é iniciada. Os participantes **podem** alternar o vídeo ou desligar.

| Configuração                | Sala do Teams      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Padrão de áudio**      | `true`          | `false`          |
| **Áudio habilitado**      | `true`          | `false`          |
| **Vídeo padrão**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Whiteboard padrão** | `false`         | `false`          |
| **Contas confiáveis**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Etapa 4: configurar o dispositivo Salas do Teams

Você pode configurar Reuniões Coordenadas em um dispositivo salas do Teams usando a tela sensível ao toque do dispositivo ou, se precisar configurar muitos dispositivos e quiser fazer isso em um local central, você pode usar um arquivo de configuração XML.

Use a planilha que você criou na etapa anterior para ajudá-lo a configurar seus dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usar a tela touch do dispositivo Salas do Teams

Para configurar Reuniões Coordenadas em um dispositivo, faça o seguinte:

1. Selecione **... Mais**  >  **Configurações.**
2. Insira a senha do Administrador e selecione **Sim.**
3. Selecione **Reuniões Coordenadas.**
4. Em **Opções,** de definir **Reunião Coordenada** como _em_.
5. Se **o padrão** de áudio na sua planilha for, de definir a opção Ativar o microfone deste dispositivo, caso `true` contrário, deixe-o _desligado._ 
6. Se **o áudio habilitado** na planilha estiver habilitado, selecione Permitir que as pessoas habilitam ao ingressar em uma reunião em Ativar o microfone deste `true` **dispositivo.**  Essa opção não poderá ser desligada se ativar o microfone **deste** dispositivo.
7. Se **o padrão do** vídeo na sua planilha for, de definir a opção Ativar a câmera deste dispositivo, caso `true` contrário, deixe-a  _desligada._
8. Se **o Vídeo habilitado na** sua planilha estiver habilitado, selecione Permitir que as pessoas habilitam ao ingressar em uma reunião em Ativar a câmera deste `true` **dispositivo.**  Essa opção não poderá ser desligada se **ativar a** câmera deste _dispositivo._
9. Se **o padrão do Whiteboard** na sua planilha for, de definir ativar o quadro de trabalho neste dispositivo para ativar, caso `true` contrário,  deixe-o _desligado._ 
10. Em **contas de dispositivo confiáveis,** digite cada UPN listado em contas **confiáveis** em sua planilha. Separe vários UPNs com vírgulas.
11. Selecione **Salvar e sair.**

Depois que você **selecionar Salvar e Sair,** o dispositivo será reiniciado e estará pronto para participar de Reuniões Coordenadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar o arquivo de configuração XML de Salas do Teams

As Reuniões Coordenadas podem ser configuradas usando o arquivo de configuração XML do dispositivo Teams `SkypeSettings.xml` Rooms. O `SkypeSettings.xml` arquivo não é um arquivo estático. Quando o dispositivo Salas do Teams é iniciar, ele verifica `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` se há um arquivo chamado `SkypeSettings.xml` . Se o arquivo existir, o dispositivo lerá e aplicará a configuração especificada no arquivo. Depois de terminar de aplicar a configuração, o arquivo será excluído. Para obter mais informações sobre o `SkypeSettings.xml` arquivo, consulte [Gerenciar configurações do console com um arquivo de configuração XML.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

Veja a seguir a sintaxe das configurações de Reuniões Coordenadas no arquivo de configuração:

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

Para configurar Reuniões Coordenadas em um dispositivo, faça o seguinte:

1. Em um editor de arquivo de texto, como o Código do Visual Studio ou o Bloco de Notas, colar o XML acima em um novo arquivo.

2. De definir cada um dos elementos XML para o valor `true` correspondente ou em sua `false` planilha. Por exemplo, se **o padrão de áudio** `true` for, de `<Audio default="true">` definida.

3. Certifique-se de `TrustedAccounts` alterar para sua lista de UPNs.

4. Salve o arquivo com o `SkypeSettings.xml` nome.

5. Coloque o arquivo na pasta do dispositivo Salas do `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` Teams. Você pode fazer isso de algumas maneiras:

    - **Copiar o arquivo para o dispositivo Salas do Teams** Você precisará habilitar o compartilhamento de arquivos e criar um compartilhamento de rede antes de copiar arquivos para seu dispositivo. Depois de fazer isso, você pode se conectar ao compartilhamento de rede e copiar o arquivo para o dispositivo. Para obter mais informações, consulte a manutenção e as operações das [Salas do Microsoft Teams.](../rooms/rooms-operations.md)
    - **Usar uma Política de Grupo** Crie uma política de grupo para copiar o arquivo para o dispositivo. Para obter mais informações, consulte Visão [Geral da Política de Grupo.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Baixar o arquivo no dispositivo Salas do Teams** Você pode fazer logoff no dispositivo usando o modo De administração e, em seguida, copiar o arquivo para o dispositivo de um compartilhamento de rede ou unidade USB. Para obter mais informações, consulte [Alternando para o modo De administração.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. Reinicie o dispositivo. Você pode fazer isso de algumas maneiras:

    - **PowerShell Remoto** Você pode executar o comando Parada Total no dispositivo usando o PowerShell Remoto. Para obter mais informações, consulte [Gerenciamento Remoto usando o PowerShell.](../rooms/rooms-operations.md)
    - **Executar Restart-Computer** Você pode executar o cmdlet no computador local e especificar o nome do `Restart-Computer` computador do dispositivo que deseja reiniciar. Para obter mais informações, consulte [Restart-Computer.](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>Etapa 5: Configurar o Surface Hub

Você pode usar o Designer de Configuração do Windows para criar um pacote de provisionamento que pode ser usado para aplicar as configurações de Reuniões Coordenadas aos seus Surface Hubs. Você colará o arquivo XML criado acima no Designer de Configuração do Windows para criar o pacote de provisionamento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Criar arquivo de configuração XML de Reuniões Coordenadas para o Surface Hub

O Designer de Configuração do Windows e o Microsoft Intune são usados para aplicar a configuração reuniões coordenadas aos surface hubs. A configuração é definida usando XML. Antes de continuar, você precisa criar o XML que será aplicado.

A seguir está a sintaxe do arquivo de configuração XML de Reuniões Coordenadas.

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

Faça o seguinte para preparar o XML para o Designer de Configuração do Windows ou o Microsoft Intune:

1. Em um editor de arquivo de texto, como o Código do Visual Studio ou o Bloco de Notas, colar o XML acima em um novo arquivo.

2. De definir cada um dos elementos XML para o valor `true` correspondente ou em sua `false` planilha. Por exemplo, se **o padrão de áudio** `true` for, de `<Audio default="true">` definida.

3. Certifique-se de `TrustedAccounts` alterar para sua lista de UPNs.

4. O Designer de Configuração do Windows exige que o XML seja em uma única linha. Remova todas as quebras de linha entre cada linha para que o XML se pareça com o seguinte:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salve o arquivo no computador.

Depois de criar seu arquivo de configuração XML, use as etapas em Gerenciar configurações do Microsoft Teams no [Surface Hub](surface-hub-manage-config.md) para aplicá-lo aos surface hubs.
