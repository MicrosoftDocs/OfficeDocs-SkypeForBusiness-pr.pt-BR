---
title: Atualizar manualmente um dispositivo salas do Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Saiba como atualizar manualmente seu dispositivo Microsoft Teams Rooms para uma versão específica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731386"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Atualizar manualmente um dispositivo salas do Microsoft Teams

O aplicativo Salas do Microsoft Teams é distribuído pela Microsoft Store. As atualizações do aplicativo são instaladas da Microsoft Store automaticamente durante a manutenção noturna; este é o método recomendado para obter atualizações. No entanto, há algumas situações em que um dispositivo salas do Teams não pode receber atualizações da Microsoft Store. Por exemplo, as políticas de segurança podem não permitir que dispositivos se conectem à Internet ou podem não permitir que os aplicativos sejam baixados da Microsoft Store. Ou talvez você queira atualizar um dispositivo antes de executar a configuração, durante o qual a Microsoft Store não está disponível.

Se você não conseguir obter atualizações da Microsoft Store, poderá usar um script de atualização de aplicativo offline do PowerShell para atualizar manualmente seus dispositivos de Salas do Teams para uma versão mais recente do aplicativo Salas do Teams. Siga as etapas deste artigo para atualizar manualmente seus dispositivos de Salas do Teams.

> [!NOTE]
> Esse processo só pode atualizar um dispositivo salas do Teams com o aplicativo Salas do Teams já instalado. Ele não pode ser usado para executar uma nova instalação. Ele também não pode ser usado para fazer downgrade do aplicativo para uma versão mais antiga. Para executar uma nova instalação do aplicativo Salas do Teams, entre em contato com o fabricante do dispositivo para ver a mídia específica ou consulte Preparar a [mídia de instalação.](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Etapa 1: baixar o script de atualização do aplicativo offline

Primeiro, baixe a versão mais recente do script de atualização do aplicativo offline. Para baixar o script, clique <https://go.microsoft.com/fwlink/?linkid=2151817> em . O script será baixado para a pasta de downloads padrão em seu dispositivo.

Os arquivos baixados podem ser marcados como bloqueados pelo Windows. Se precisar executar o script sem nenhuma interação, será necessário desbloquear o script. Para desbloquear o script, faça o seguinte:

1. Clique com o botão direito do mouse no arquivo no Explorador de Arquivos
2. Clique **em Propriedades**
3. Selecione **Desbloquear**
4. Clique **em OK**

Para desbloquear o script usando o PowerShell, consulte [Desbloquear Arquivo.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

Depois que o script de atualização do aplicativo offline for baixado, transfira o arquivo para o dispositivo Salas do Teams. Você pode transferir um arquivo para o dispositivo usando uma unidade USB ou acessando o arquivo de um compartilhamento de arquivos de rede enquanto estiver no Modo de Administração no dispositivo. Certifique-se de observar onde você salvou o arquivo no dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Etapa 2: executar o script para atualizar o aplicativo Salas do Teams

O script de atualização do aplicativo offline precisa ser executado a partir de um prompt de comando elevado enquanto o usuário do Skype (o usuário no qual o aplicativo é executado) ainda está dentro. Para obter mais informações sobre como fazer logon em uma conta de administrador para usar o prompt de comando elevado enquanto o usuário do Skype ainda estiver conectado, consulte Alternar para o Modo de Administração e voltar quando o aplicativo Salas do [Microsoft Teams](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)estiver em execução.

Faça o seguinte para executar o script de um prompt de comando elevado:

1. Alternar para o Modo de Administração
2. Clique no ícone Iniciar, digite **Prompt de Comando** e selecione Executar como **administrador**
3. Execute o seguinte comando onde inclui o caminho completo para o `<path to script>` script e o nome do arquivo de script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Por exemplo, se o arquivo de script estiver localizado em e o nome do arquivo `C:\Users\Admin\Downloads` de script `MTR-Update-4.5.6.7.ps1` estiver, execute o seguinte comando:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Permitir que o script seja executado. Quando terminar, o script reiniciará o dispositivo Salas do Teams.

Você também pode executar o script usando o PowerShell Remoto. Para obter mais informações sobre como usar o PowerShell Remoto com dispositivos de Salas do Teams, consulte Gerenciamento [Remoto usando o PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Etapa 3: verificar se o aplicativo foi atualizado com êxito

Se o script for executado com êxito, o dispositivo será reinicializado no aplicativo Salas do Teams.

Se o script encontrar um problema, ele indicará qual é o problema na linha de comando e gravará sua saída em um arquivo. Siga as instruções fornecidas pelo script. Se precisar entrar em contato com o Suporte da Microsoft, inclua o arquivo de log junto com a solicitação de suporte. O script fornecerá o caminho para o arquivo de log.
