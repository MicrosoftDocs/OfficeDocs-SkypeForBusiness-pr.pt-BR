---
title: Configurar reuniões coordenadas com o Salas do Microsoft Teams e o Surface Hub
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
description: Configure Salas do Teams dispositivos e o Surface Hub para ingressar em reuniões quando um dispositivo ou outro ingressar em uma reunião.
ms.openlocfilehash: 1f249e9bd0321c9e8afd984aca90f902ad80d444
ms.sourcegitcommit: 644374fcad6372494e87d729de690af4c060f635
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2022
ms.locfileid: "67054932"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar reuniões coordenadas com o Salas do Microsoft Teams e o Surface Hub

Se você tiver um ou mais Salas do Microsoft Teams ou Surface Hubs em uma sala de reunião, poderá configurar Reuniões Coordenadas. As Reuniões Coordenadas permitem que você configure seus dispositivos Salas do Teams e Surface Hubs para que, quando você ingressar em uma reunião em um dispositivo, os outros dispositivos na sala também sejam ingressados na mesma reunião. Você pode configurar suas câmeras, alto-falantes e microfones para que aqueles que oferecem aos participantes a melhor experiência sejam habilitados enquanto outros estão desabilitados. Isso evita o temido eco e o ruído de comentários que os participantes podem experimentar ao adicionar vários dispositivos a uma reunião.

Para configurar reuniões coordenadas, você precisa verificar se seus dispositivos Salas do Teams e Surface Hubs já estão configurados corretamente para participar de reuniões. O mais importante é que cada dispositivo precisa ter sua própria caixa de correio da sala do Exchange. Para obter informações sobre como configurá-los, consulte os seguintes artigos:

- [Implantar Salas do Microsoft Teams](../rooms/rooms-deploy.md)
- [Criar uma conta de dispositivo do Surface Hub 2S](/surface-hub/surface-hub-2s-account)

Depois de confirmar que seus dispositivos Salas do Teams Surface Hubs podem aceitar reuniões automaticamente e ingressá-las com êxito, você pode configurar Reuniões Coordenadas.

As etapas a seguir devem ser concluídas separadamente para cada sala de reunião.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Etapa 1: Planejar sua experiência de Reunião Coordenada

Antes de fazer alterações de configuração, você precisa decidir quais dispositivos fazerão o que em cada sala de reunião. Ou seja, para uma determinada sala de reunião, você precisa decidir qual dispositivo terá o microfone, a câmera e o quadro de comunicações ativos. A maneira como você configura seus dispositivos depende do seu ambiente específico, mas aqui estão algumas recomendações gerais para começar:

- **Dispositivo Salas do Teams** microfone
- **Câmera** Salas do Teams dispositivo (ativado por padrão) e Surface Hub (desativado por padrão, mas com permissão para ser ativado pelos participantes)
- **Whiteboard** Surface Hub

> [!IMPORTANT]
> Certifique-se de habilitar o microfone somente em um dispositivo. Se você habilita-lo em mais de um dispositivo, você experimentará o eco de áudio e os comentários.

## <a name="step-2-get-your-devices-upns"></a>Etapa 2: Obter os UPNs dos dispositivos

Ao configurar uma experiência de Reunião Coordenada em uma sala de reunião, você precisa informar os dispositivos Salas do Teams e Surface Hubs nessa sala com os quais os dispositivos devem ser coordenados. Isso é feito adicionando o NOME UPN dos dispositivos com os que ele deve coordenar à sua configuração. Se você não souber os UPNs de cada um dos dispositivos que deseja configurar para Reuniões Coordenadas, poderá encontrá-los usando o Centro de administração do Microsoft 365. 

Você precisa receber uma função de administrador para acessar o Centro de administração do Microsoft 365. Para obter mais informações, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

Para obter os UPNs de seus dispositivos Salas do Teams e Surface Hubs, faça o seguinte:

1. Entre no Centro de administração do Microsoft 365 visitandohttps://admin.microsoft.com.
2. Vá para **usuários** > **ativos**.
3. Localize o nome do dispositivo Salas do Teams ou Surface Hub na coluna Nome de  exibição (você pode usar a caixa  Pesquisar se tiver muitos usuários).
4. Localize o UPN na coluna **Nome** de usuário (ele será semelhante a alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Repita isso para cada dispositivo que participará de Reuniões Coordenadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Etapa 3: Criar uma planilha de implantação

Depois de planejar sua experiência de Reunião Coordenada e juntar uma lista dos UPNs dos dispositivos, é uma boa ideia criar uma planilha de implantação. Uma planilha de implantação ajudará você a visualizar a configuração que deseja definir em todos os seus dispositivos, permitindo que você valide suas escolhas e verifique se há erros.

Em um aplicativo de planilha, adicione linhas para o seguinte na primeira coluna:

| Configuração                | Descrição      |
|------------------------|-----------------|
| **Padrão de áudio**      | Determina em qual dispositivo o microfone estará ativo quando uma reunião for iniciada. Somente um dispositivo (normalmente um dispositivo Salas do Teams) `true` `false` pode ter esse campo definido, enquanto o restante dos dispositivos deve ter esse campo definido para evitar eco de áudio e comentários.          |
| **Áudio habilitado**      | Determina se os participantes de uma reunião podem ativar ou desativar o microfone. Os dispositivos **nos** `false` `false` quais o padrão de áudio está definido devem ter essa configuração definida para que os participantes não possam ativar acidentalmente um microfone e causar eco de áudio ou comentários.<p>Se **o padrão** de áudio for definido como `true`, essa configuração será ignorada e os participantes poderão ativar ou desativar o mudo do microfone.          |
| **Padrão de vídeo**      | Determina em qual dispositivo a câmera estará ativa quando uma reunião for iniciada. Para obter a melhor experiência, recomendamos que apenas o Salas do Teams dispositivo `true` seja definido como enquanto todos os outros dispositivos estão definidos como `false`.          |
| **Vídeo habilitado**      | Determina se os participantes de uma reunião podem ativar ou desativar a câmera. Você pode definir isso como em `true` qualquer outro dispositivo no evento em que os participantes desejem compartilhar diferentes perspectivas de vídeo (por exemplo, se um participante estiver usando o quadro de comunicações do Surface Hub). Se você não quiser que os participantes ativem ou desativem uma câmera em um dispositivo, defina isso como `false`.<p> Se **o padrão** de Vídeo for definido como `true`, essa configuração será ignorada e os participantes poderão ativar ou desativar a câmera.         |
| **Padrão do quadro de comunicações** | Determina se o Salas do Teams exibirá um quadro de comunicações compartilhado por um dos participantes da reunião. Recomendamos que você defina isso como `false` se você tiver um Surface Hub `true` e se não tiver um. Essa configuração não tem efeito nos Surface Hubs. Os Surface Hubs sempre exibirão um quadro de comunicações compartilhado pelos participantes da reunião.         |
| **Quadro de comunicações habilitado** | Determina se os participantes de uma reunião podem ativar ou desativar o quadro de comunicações. Se você não quiser que os participantes ativem ou desativem o quadro de comunicações em um dispositivo, defina isso como `false`. <p>Se **o padrão do Quadro** de Comunicações for definido como `true`, essa configuração será ignorada e os participantes poderão ativar ou desativar o quadro de comunicações.
| **Contas confiáveis**   | Esta é uma lista separada por vírgulas de UPNs para cada dispositivo da Sala do Teams ou Surface Hub do qual o dispositivo deve aceitar solicitações de ingresso na reunião ou para quais solicitações de ingresso na reunião devem ser enviadas. |

Em colunas subsequentes, adicione cada um dos seus dispositivos Salas do Teams e Surface Hubs. Em cada coluna, preencha os valores que correspondem à experiência desejada para a sala de reunião. Veja um exemplo com um dispositivo Salas do Teams e um Surface Hub:

- Dispositivo do Teams
  - Áudio e vídeo são **ativados quando** uma reunião é iniciada. Os participantes **podem** ativar ou desativar áudio e vídeo.
  - A exibição de um quadro de comunicações compartilhado está desativada.
- Surface Hub
  - O áudio é **desativado quando** uma reunião é iniciada. Os participantes **não podem ativar** ou desativar o áudio.
  - O vídeo é **desativado quando** uma reunião é iniciada. Os participantes **podem** ativar ou desativar o vídeo.

| Configuração                | Sala do Teams      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Padrão de áudio**      | `true`          | `false`          |
| **Áudio habilitado**      | `true`          | `false`          |
| **Padrão de vídeo**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Padrão do quadro de comunicações** | `false`         | `false`          |
| **Contas confiáveis**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Etapa 4: Configurar Salas do Teams dispositivo

Você pode configurar Reuniões Coordenadas em um dispositivo Salas do Teams usando a tela sensível ao toque do dispositivo ou, se precisar configurar muitos dispositivos e desejar fazer isso em um local central, poderá usar um arquivo de configuração XML.

Use a planilha que você criou na etapa anterior para ajudá-lo a configurar seus dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usar a Salas do Teams tela sensível ao toque do dispositivo

Para configurar Reuniões Coordenadas em um dispositivo, faça o seguinte:

1. Selecione **... Mais** > **Configurações**.
2. Insira a senha do Administrador e selecione **Sim**.
3. Selecione **Reuniões Coordenadas**.
4. Em **Opções**, defina **a Reunião Coordenada** como _ativada_.
5. Se **o padrão** de áudio na planilha for `true`, defina Ativar o microfone **deste** dispositivo, caso contrário, deixe-o _desativado_.
6. Se **o áudio habilitado** na planilha `true`estiver, selecione Permitir que  as pessoas habilitem ao ingressar em uma reunião em Ativar **o microfone deste dispositivo**. Essa opção não poderá ser desativada se o microfone **deste** dispositivo estiver ativado.
7. Se **o padrão** de vídeo na planilha for `true`, defina Ativar a câmera **deste** dispositivo, caso contrário, _deixe-a desativada_.
8. Se **o Vídeo habilitado** na planilha `true`estiver, selecione Permitir que  as pessoas habilitem ao ingressar em uma reunião em Ativar **a câmera deste dispositivo**. Essa opção não poderá ser desativada se **a opção Ativar a** câmera deste dispositivo estiver _ativada_.
9. Se **o padrão do Quadro** de Comunicações na `true`planilha for , defina **Ativar o quadro de** comunicações neste dispositivo como _ativado_; caso contrário, _deixe-o desativado_.
10. Em **Contas de dispositivo confiável**, digite cada UPN listado em **contas confiáveis** em sua planilha. Separe vários UPNs com vírgulas.
11. No dispositivo confiável, desative a proximidade e a sala remota. 
12. Selecione **Salvar e sair**.

Depois de selecionar **Salvar e sair**, o dispositivo será reiniciado e estará pronto para participar de Reuniões Coordenadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar o arquivo Salas do Teams de configuração XML

As Reuniões Coordenadas podem ser configuradas usando o Salas do Teams de configuração `SkypeSettings.xml` XML do dispositivo. O `SkypeSettings.xml` arquivo não é um arquivo estático. Quando o Salas do Teams é iniciado, ele faz o checks-in de `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` um arquivo chamado `SkypeSettings.xml`. Se o arquivo existir, o dispositivo lerá e aplicará a configuração especificada no arquivo. Depois de terminar de aplicar a configuração, o arquivo será excluído. Para obter mais informações sobre o arquivo `SkypeSettings.xml` , consulte [Gerenciar configurações de console com um arquivo de configuração XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

A seguir está a sintaxe das configurações de Reuniões Coordenadas no arquivo de configuração:

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

1. Em um editor de arquivo de texto, como Visual Studio Code ou Bloco de Notas, cole o XML acima em um novo arquivo.

2. Defina cada um dos elementos XML para o valor correspondente `true` ou `false` em sua planilha. Por exemplo, se **o padrão de áudio** for , `true`defina `<Audio default="true">`.

3. Certifique-se de alterar `TrustedAccounts` para sua lista de UPNs.

4. Salve o arquivo com o nome `SkypeSettings.xml`.

5. Coloque o arquivo na pasta Salas do Teams do dispositivo`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Você pode fazer isso de algumas maneiras:

    - **Copie o arquivo para seu dispositivo Salas do Teams** você precisará habilitar o compartilhamento de arquivos e criar um compartilhamento de rede antes de copiar arquivos para seu dispositivo. Depois de fazer isso, você pode se conectar ao compartilhamento de rede e copiar o arquivo para o dispositivo. Para obter mais informações, [consulte Salas do Microsoft Teams manutenção e operações](../rooms/rooms-operations.md).
    - **Use um Política de Grupo** Criar uma política de grupo para copiar o arquivo para o dispositivo. Para obter mais informações, [consulte Política de Grupo visão geral](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Baixe o arquivo no dispositivo Salas do Teams** Você pode fazer logon no dispositivo usando o modo Administração e, em seguida, copiar o arquivo para o dispositivo de um compartilhamento de rede ou unidade USB. Para obter mais informações, [consulte Alternar para Administração modo](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Reinicie o dispositivo. Você pode fazer isso de duas maneiras:

    - **PowerShell remoto** Você pode executar o comando Desligamento no dispositivo usando o PowerShell Remoto. Para obter mais informações, consulte [Gerenciamento Remoto usando o PowerShell](../rooms/rooms-operations.md).
    - **Executar Reiniciar Computador** Você pode executar o `Restart-Computer` cmdlet no computador local e especificar o nome do computador do dispositivo que deseja reiniciar. Para obter mais informações, consulte [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Etapa 5: Configurar o Surface Hub

Você pode usar o Designer de Configuração do Windows para criar um pacote de provisionamento que pode ser usado para aplicar as configurações de Coordenação de Reuniões aos Surface Hubs. Você colará o arquivo XML criado acima no Designer de Configuração do Windows para criar o pacote de provisionamento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Criar arquivo de configuração XML de Reuniões Coordenadas para o Surface Hub

O Designer de Configuração do Windows e Microsoft Intune são usados para aplicar a configuração de Reuniões Coordenadas aos Surface Hubs. A configuração é definida usando XML. Antes de prosseguir, você precisa criar o XML que será aplicado.

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

Faça o seguinte para preparar o XML para o Designer de Configuração do Windows ou Microsoft Intune:

1. Em um editor de arquivo de texto, como Visual Studio Code ou Bloco de Notas, cole o XML acima em um novo arquivo.

2. Defina cada um dos elementos XML para o valor correspondente `true` ou `false` em sua planilha. Por exemplo, se **o padrão de áudio** for , `true`defina `<Audio default="true">`.

3. Certifique-se de alterar `TrustedAccounts` para sua lista de UPNs.

4. O Designer de Configuração do Windows exige que o XML esteja em uma única linha. Remova todas as quebras de linha entre cada linha para que o XML tenha a seguinte aparência:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salve o arquivo no computador.

Depois de criar o arquivo de configuração XML, use as etapas em Gerenciar configurações do [Microsoft Teams no Surface Hub](surface-hub-manage-config.md) para aplicá-lo aos Surface Hubs.
