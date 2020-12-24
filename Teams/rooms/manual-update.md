---
title: Atualizar manualmente um dispositivo de salas do Microsoft Teams
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
description: Saiba como atualizar manualmente seu dispositivo de salas do Microsoft Teams para uma versão específica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731386"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Atualizar manualmente um dispositivo de salas do Microsoft Teams

O aplicativo salas do Microsoft Teams é distribuído pela Microsoft Store. As atualizações do aplicativo são instaladas automaticamente da Microsoft Store durante a manutenção noturna; Esse é o método recomendado para obter atualizações. No entanto, há algumas situações em que um dispositivo de salas de equipe não pode receber atualizações da Microsoft Store. Por exemplo, as políticas de segurança podem não permitir que os dispositivos se conectem à Internet ou podem não permitir que os aplicativos sejam baixados da Microsoft Store. Ou talvez você queira atualizar um dispositivo antes de executar a instalação, durante a qual a Microsoft Store não está disponível.

Se não for possível obter atualizações da Microsoft Store, você poderá usar um script do PowerShell de atualização de aplicativo offline para atualizar manualmente seus dispositivos de salas de equipe para uma versão mais recente do aplicativo salas de equipe. Siga as etapas deste artigo para atualizar manualmente seus dispositivos de salas de equipe.

> [!NOTE]
> Esse processo somente pode atualizar um dispositivo de salas de equipe com o aplicativo salas de equipe já instalado. Ele não pode ser usado para executar uma nova instalação. Ele também não pode ser usado para fazer o downgrade do aplicativo para uma versão mais antiga. Para executar uma nova instalação do aplicativo salas de equipe, entre em contato com o fabricante do dispositivo para ver a mídia específica dele ou consulte [preparar a mídia de instalação](console.md#prepare-the-installation-media).

## <a name="step-1-download-the-offline-app-update-script"></a>Etapa 1: baixar o script de atualização do aplicativo offline

Primeiro, baixe a versão mais recente do script de atualização do aplicativo offline. Para baixar o script, clique em <https://go.microsoft.com/fwlink/?linkid=2151817> . O script será baixado para a pasta de downloads padrão em seu dispositivo.

Os arquivos baixados podem ser marcados como bloqueados pelo Windows. Se você precisar executar o script sem qualquer interação, será necessário desbloquear o script. Para desbloquear o script, faça o seguinte:

1. Clique com o botão direito do mouse no arquivo no explorador de arquivos
2. Clique em **Propriedades**
3. Selecione **desbloquear**
4. Clique em **OK**

Para desbloquear o script usando o PowerShell, confira [desbloquear-arquivo](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Após o download do script de atualização do aplicativo offline, transfira o arquivo para o dispositivo de salas de equipe. Você pode transferir um arquivo para o dispositivo usando uma unidade USB ou acessando o arquivo a partir de um compartilhamento de arquivo de rede enquanto estiver no modo de administração do dispositivo. Lembre-se de anotar onde você salva o arquivo no dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Etapa 2: executar o script para atualizar o aplicativo salas de equipe

O script de atualização de aplicativo offline precisa ser executado em um prompt de comando elevado enquanto o usuário do Skype (o usuário em que o aplicativo é executado) ainda está conectado. Para obter mais informações sobre como fazer logon em uma conta de administrador para usar o prompt de comando elevado enquanto o usuário do Skype ainda estiver conectado, consulte [alternando para o modo de administrador e de volta quando o aplicativo salas do Microsoft Teams está em execução](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).

Siga este procedimento para executar o script a partir de um prompt de comando elevado:

1. Alternar para o modo de administrador
2. Clique no ícone iniciar, digite **prompt de comando** e selecione **Executar como administrador**
3. Execute o seguinte comando onde `<path to script>` inclui o caminho completo para o script e o nome do arquivo de script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Por exemplo, se o arquivo de script estiver localizado em `C:\Users\Admin\Downloads` e o nome do arquivo de script for `MTR-Update-4.5.6.7.ps1` , execute o seguinte comando:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Permitir que o script seja executado. Quando terminar, o script reiniciará o dispositivo de salas de equipe.

Você também pode executar o script usando o PowerShell remoto. Para obter mais informações sobre como usar o PowerShell remoto com dispositivos de salas de equipe, consulte [gerenciamento remoto usando o PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Etapa 3: Verifique se o aplicativo foi atualizado com êxito

Se o script for executado com êxito, o dispositivo será reiniciado no aplicativo salas de equipe.

Se o script encontrar um problema, ele indicará qual é o problema na linha de comando e gravará a saída em um arquivo. Siga as instruções fornecidas pelo script. Se precisar entrar em contato com o suporte da Microsoft, certifique-se de incluir o arquivo de log juntamente com a solicitação de suporte. O script lhe fornecerá o caminho para o arquivo de log.
