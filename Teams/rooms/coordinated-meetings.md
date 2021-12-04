---
title: Configurar reuniões coordenadas com Salas do Microsoft Teams e Surface Hub
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
description: Configure Salas do Teams dispositivos e Surface Hub participar de reuniões quando um dispositivo ou outro ingressar em uma reunião.
ms.openlocfilehash: 1f7aca3d8921d400a5b034c702f1201ee48996bc
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306166"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar reuniões coordenadas com Salas do Microsoft Teams e Surface Hub

Se você tiver um ou mais Salas do Microsoft Teams ou Surface Hubs em uma sala de reunião, poderá configurar Reuniões Coordenadas. Reuniões coordenadas permitem configurar seus dispositivos Salas do Teams e Surface Hubs para que, quando você ingressar em uma reunião em um dispositivo, os outros dispositivos na sala também sejam ingressados na mesma reunião. Você pode configurar suas câmeras, alto-falantes e microfones para que os que dão aos participantes a melhor experiência sejam habilitados enquanto outros estão desabilitados. Isso evita que os participantes com medo de eco e ruído de feedback possam experimentar ao adicionar vários dispositivos a uma reunião.

Para configurar Reuniões Coordenadas, você precisa garantir que seus dispositivos Salas do Teams e Surface Hubs já estão configurados corretamente para participar das reuniões. O mais importante é que cada dispositivo precisa ter sua própria caixa de correio Exchange sala. Para obter informações sobre como defini-los, consulte os seguintes artigos:

- [Implantar Salas do Microsoft Teams](../rooms/rooms-deploy.md)
- [Criar Surface Hub de dispositivo 2S](/surface-hub/surface-hub-2s-account)

Depois de confirmar que seus dispositivos Salas do Teams e Surface Hubs podem aceitar automaticamente reuniões e jun-las com êxito, você pode configurar Reuniões Coordenadas.

As etapas a seguir devem ser concluídas para cada sala de reunião separadamente.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Etapa 1: Planejar sua experiência de Reunião Coordenada

Antes de fazer alterações de configuração, você precisa decidir quais dispositivos irão fazer o que em cada sala de reunião. Ou seja, para uma determinada sala de reunião, você precisa decidir qual dispositivo terá o microfone, câmera e quadro de trabalho ativo. A forma como você configura seus dispositivos depende do seu ambiente específico, mas aqui estão algumas recomendações gerais para começar:

- **Dispositivo Salas do Teams** microfone
- **Dispositivo** Salas do Teams câmera (por padrão) e Surface Hub (desligado por padrão, mas permitido para ser ligado pelos participantes)
- **Quadro de** Surface Hub

> [!IMPORTANT]
> Certifique-se de habilitar o microfone somente em um dispositivo. Se você habilita-lo em mais de um dispositivo, você experimentará eco de áudio e comentários.

## <a name="step-2-get-your-devices-upns"></a>Etapa 2: Obter UPNs de seus dispositivos

Quando você configura uma experiência de Reunião Coordenada em uma sala de reunião, precisa dizer aos dispositivos Salas do Teams e Surface Hubs nessa sala com os quais os dispositivos devem ser coordenados. Isso é feito adicionando o nome principal do usuário (UPN) dos dispositivos com os que ele deve coordenar à configuração. Se você não conhece os UPNs para cada um dos dispositivos que deseja configurar para Reuniões Coordenadas, você pode encontrá-los usando o Centro de administração do Microsoft 365. 

Você precisa ter uma função de administrador para acessar o Centro de administração do Microsoft 365. Para obter mais informações, consulte [Sobre funções de administrador](/microsoft-365/admin/add-users/about-admin-roles).

Para obter os UPNs de seus dispositivos Salas do Teams e Surface Hubs, faça o seguinte:

1. Entre no Centro de administração do Microsoft 365 visitando https://admin.microsoft.com .
2. Vá para **Usuários**  >  **Usuários ativos**.
3. Encontre o nome do dispositivo Salas do Teams ou Surface Hub na  coluna Nome de exibição (você pode usar a caixa Pesquisar se tiver muitos usuários). 
4. Encontre o UPN na coluna **Nome** de Usuário (ele será parecido com alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Repita isso para cada dispositivo que participará de Reuniões Coordenadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Etapa 3: Criar uma planilha de implantação

Depois de planejar sua experiência de Reunião Coordenada e reunir uma lista dos UPNs de seus dispositivos, é uma boa ideia criar uma planilha de implantação. Uma planilha de implantação ajudará você a visualizar a configuração que você deseja definir em todos os seus dispositivos, permitindo que você valide suas escolhas e verifique se há erros.

Em um aplicativo de planilha, adicione linhas para o seguinte na primeira coluna:

| Configuração                | Descrição      |
|------------------------|-----------------|
| **Padrão de áudio**      | Determina em qual dispositivo o microfone estará ativo quando uma reunião for iniciada. Somente um dispositivo (normalmente um dispositivo Salas do Teams) pode ter esse campo definido como enquanto o restante dos dispositivos deve ter esse campo definido para evitar eco de áudio e `true` `false` comentários.          |
| **Áudio habilitado**      | Determina se os participantes de uma reunião podem alternar ou desligar o microfone. Dispositivos nos quais **o padrão** de áudio é definido devem ter essa configuração definida para que os participantes não possam ativar acidentalmente um microfone e causar eco de áudio `false` ou `false` comentários.<p>Se **o padrão de** áudio estiver definido como , essa configuração será ignorada e os participantes poderão `true` silenciar ou desativar o microfone.          |
| **Padrão de vídeo**      | Determina em qual dispositivo a câmera estará ativa quando uma reunião for iniciada. Para a melhor experiência, recomendamos que apenas o dispositivo Salas do Teams seja definido como enquanto todos os outros `true` dispositivos estão definidos como `false` .          |
| **Vídeo habilitado**      | Determina se os participantes de uma reunião podem alternar ou desligar a câmera. Você pode definir isso como em qualquer outro dispositivo no evento em que os participantes do evento quiserem compartilhar diferentes perspectivas de vídeo (como se um participante estiver usando o quadro de Surface Hub `true` de vídeo). Se você não quiser que os participantes a liguem ou desliguem uma câmera em um dispositivo, de definir isso como `false` .<p> Se **o padrão de** vídeo estiver definido como , essa configuração será ignorada e os participantes poderão ativar ou desativar a `true` câmera.         |
| **Padrão do quadro de dados** | Determina se o dispositivo Salas do Teams exibirá um quadro de negociação compartilhado por um dos participantes da reunião. É recomendável definir isso como se você tiver uma Surface Hub `false` e se você não tiver `true` um. Essa configuração não tem efeito nos Surface Hubs. Os Surface Hubs sempre exibirão um quadro de trabalho compartilhado pelos participantes da reunião.         |
| **Quadro de trabalho habilitado** | Determina se os participantes de uma reunião podem alternar ou desligar o quadro de dados. Se você não quiser que os participantes a liguem ou desliguem o quadro de dados em um dispositivo, de definir isso como `false` . <p>Se **o padrão do quadro** de branco estiver definido como , essa configuração será ignorada e os participantes poderão ativar ou desativar o quadro de `true` trabalho.
| **Contas confiáveis**   | Esta é uma lista separada por vírgulas de UPNs para cada dispositivo de sala Teams ou Surface Hub de onde o dispositivo deve aceitar solicitações de junção de reunião ou para quais solicitações de junção de reunião devem ser enviadas. |

Em colunas subsequentes, adicione cada um dos dispositivos Salas do Teams e Surface Hubs. Em cada coluna, preencha os valores que correspondem à experiência que você deseja para a sala de reunião. Veja um exemplo com um Salas do Teams e um Surface Hub:

- Teams dispositivo
  - Áudio e vídeo são **acionados** quando uma reunião é iniciada. Os participantes **podem** alternar áudio e vídeo para cima ou para fora.
  - A exibição de um quadro de branco compartilhado está desligada.
- Surface Hub
  - O áudio é **desligado quando** uma reunião é iniciada. Os participantes **não podem alternar** áudio ou desligar.
  - O vídeo é **desligado quando** uma reunião é iniciada. Os participantes **podem** alternar ou desligar o vídeo.

| Configuração                | Teams Room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Padrão de áudio**      | `true`          | `false`          |
| **Áudio habilitado**      | `true`          | `false`          |
| **Padrão de vídeo**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Padrão do quadro de dados** | `false`         | `false`          |
| **Contas confiáveis**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Etapa 4: Configurar Salas do Teams dispositivo

Você pode configurar Reuniões Coordenadas em um dispositivo Salas do Teams usando a tela touch do dispositivo ou, se precisar configurar muitos dispositivos e quiser fazer isso em um local central, você pode usar um arquivo de configuração XML.

Use a planilha criada na etapa anterior para ajudá-lo a configurar seus dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usar a Salas do Teams de toque do dispositivo Salas do Teams do dispositivo

Para configurar Reuniões Coordenadas em um dispositivo, faça o seguinte:

1. Selecione **... Mais**  >  **Configurações**.
2. Insira a senha administrador e selecione **Sim**.
3. Selecione **Reuniões Coordenadas**.
4. Em **Opções,** de definir **Reunião Coordenada** como _em_.
5. Se **o padrão de** áudio em sua planilha for , de definir Ativar o microfone deste dispositivo como, caso `true` contrário, deixe-o  _desligado_.
6. Se **o áudio habilitado na** planilha for , selecione Permitir que as pessoas `true` **habilitam** ao ingressar em uma reunião em Ativar o microfone deste **dispositivo.** Essa opção não poderá ser desligada se **o** microfone deste dispositivo estiver definido como ligado.
7. Se **o padrão de** vídeo em sua planilha for , de definir Ativar a câmera deste dispositivo como, caso `true` contrário, deixe-a  _desligada_.
8. Se **o vídeo habilitado na** planilha for , selecione Permitir que as pessoas `true` **habilitam** ao ingressar em uma reunião em Ativar a **câmera deste dispositivo.** Essa opção não poderá ser desligada se **Ativar** a câmera deste dispositivo estiver _definida_ como .
9. Se **o padrão do quadro** de trabalho for , de definir Ativar o quadro de trabalho neste dispositivo como , caso `true` contrário, deixe-o _fora_.  
10. Em **Contas de dispositivo confiáveis,** digite cada UPN listado em contas **confiáveis** em sua planilha. Separe vários UPNs com vírgulas.
11. Selecione **Salvar e sair**.

Depois de selecionar **Salvar e sair,** o dispositivo será reiniciado e estará pronto para participar de Reuniões Coordenadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar o arquivo Salas do Teams configuração XML

Reuniões coordenadas podem ser configuradas usando o arquivo de configuração XML do Salas do Teams `SkypeSettings.xml` do dispositivo. O `SkypeSettings.xml` arquivo não é um arquivo estático. Quando o Salas do Teams dispositivo é a iniciar, ele faz o controle `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` de um arquivo chamado `SkypeSettings.xml` . Se o arquivo existir, o dispositivo lerá e aplicará a configuração especificada no arquivo. Após a aplicação da configuração, o arquivo é excluído. Para obter mais informações sobre o `SkypeSettings.xml` arquivo, consulte [Gerenciar configurações de console com um arquivo de configuração XML.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

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

1. Em um editor de arquivos de texto, como Visual Studio Code ou Bloco de notas, colar o XML acima em um novo arquivo.

2. De definir cada um dos elementos XML para o valor `true` correspondente `false` ou na planilha. Por exemplo, se **o padrão de áudio** for , de definir `true` `<Audio default="true">` .

3. Certifique-se de alterar `TrustedAccounts` para sua lista de UPNs.

4. Salve o arquivo com o nome `SkypeSettings.xml` .

5. Coloque o arquivo na pasta Salas do Teams do `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` dispositivo. Você pode fazer isso de algumas maneiras:

    - **Copie o arquivo para seu dispositivo Salas do Teams** você precisará habilitar o compartilhamento de arquivos e criar um compartilhamento de rede antes de copiar arquivos para seu dispositivo. Depois de fazer isso, você pode se conectar ao compartilhamento de rede e copiar o arquivo para o dispositivo. Para obter mais informações, [consulte Salas do Microsoft Teams manutenção e operações](../rooms/rooms-operations.md).
    - **Usar uma Política de Grupo** Crie uma política de grupo para copiar o arquivo para o dispositivo. Para obter mais informações, consulte [Visão geral da Política de Grupo.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Baixe o arquivo no dispositivo Salas do Teams** Você pode fazer logoff no dispositivo usando o modo Admin e, em seguida, copiar o arquivo para o dispositivo de um compartilhamento de rede ou unidade USB. Para obter mais informações, consulte [Alternando para o modo De administração](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Reinicie o dispositivo. Você pode fazer isso de duas maneiras:

    - **PowerShell remoto** Você pode executar o comando Desligamento no dispositivo usando o PowerShell Remoto. Para obter mais informações, consulte [Gerenciamento Remoto usando o PowerShell](../rooms/rooms-operations.md).
    - **Executar Restart-Computer** Você pode executar o cmdlet no computador local e especificar o nome do `Restart-Computer` computador do dispositivo que deseja reiniciar. Para obter mais informações, consulte [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Etapa 5: Configurar Surface Hub

Você pode usar Windows Designer de Configuração para criar um pacote de provisionamento que você pode usar para aplicar configurações de Reuniões de Coordenação aos Surface Hubs. Você colará o arquivo XML criado acima no Windows Configuration Designer para criar o pacote de provisionamento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Criar arquivo de configuração XML de Reuniões Coordenadas para Surface Hub

Tanto Windows Designer de Configuração quanto Microsoft Intune são usados para aplicar a configuração reuniões coordenadas aos surface hubs. A configuração é definida usando XML. Antes de ir além, você precisa criar o XML que será aplicado.

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

Faça o seguinte para preparar o XML para Windows Configuration Designer ou Microsoft Intune:

1. Em um editor de arquivos de texto, como Visual Studio Code ou Bloco de notas, colar o XML acima em um novo arquivo.

2. De definir cada um dos elementos XML para o valor `true` correspondente `false` ou na planilha. Por exemplo, se **o padrão de áudio** for , de definir `true` `<Audio default="true">` .

3. Certifique-se de alterar `TrustedAccounts` para sua lista de UPNs.

4. Windows Designer de Configuração exige que o XML seja em uma única linha. Remova todas as quebras de linha entre cada linha para que o XML se pareça com o seguinte:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salve o arquivo em seu computador.

Depois de criar seu arquivo de configuração XML, use as etapas em [Gerenciar](surface-hub-manage-config.md) Microsoft Teams configurações no Surface Hub para aplicá-lo aos Surface Hubs.