---
title: Atualizar manualmente um Salas do Microsoft Teams dispositivo
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Saiba como atualizar manualmente seu dispositivo Salas do Microsoft Teams para uma versão específica.
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267636"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Atualizar manualmente um Salas do Microsoft Teams dispositivo

O Salas do Microsoft Teams aplicativo é distribuído por meio da Microsoft Store. Atualizações para o aplicativo são instalados da Microsoft Store automaticamente durante a manutenção noturna; esse é o método recomendado para obter atualizações. No entanto, há algumas situações em que um Salas do Teams não pode receber atualizações da Microsoft Store. Por exemplo, as políticas de segurança podem não permitir que os dispositivos se conectem à Internet ou podem não permitir que os aplicativos sejam baixados da Microsoft Store. Ou talvez você queira atualizar um dispositivo antes de executar a instalação, durante o qual a Microsoft Store não está disponível.

Se você não conseguir obter atualizações da Microsoft Store, poderá usar um script do PowerShell de atualização de aplicativo offline para atualizar manualmente seus dispositivos Salas do Teams para uma versão mais recente do aplicativo Salas do Teams. Siga as etapas neste artigo para atualizar manualmente seus Salas do Teams dispositivos.

> [!NOTE]
> Esse processo só pode atualizar um Salas do Teams com o aplicativo Salas do Teams já instalado. Ele não pode ser usado para executar uma nova instalação. Ele também não pode ser usado para fazer downgrade do aplicativo para uma versão mais antiga. Para executar uma nova instalação do aplicativo Salas do Teams, entre em contato com o fabricante do dispositivo para obter uma mídia específica dele.

## <a name="step-1-download-the-offline-app-update-script"></a>Etapa 1: Baixar o script de atualização de aplicativo offline

Primeiro, baixe a versão mais recente do script de atualização de aplicativo offline. Para baixar o script, clique em <https://go.microsoft.com/fwlink/?linkid=2151817>. O script será baixado para a pasta de downloads padrão em seu dispositivo.

Os arquivos baixados podem ser marcados como bloqueados pelo Windows. Se você precisar executar o script sem nenhuma interação, será necessário desbloquear o script. Para desbloquear o script, faça o seguinte:

1. Clique com o botão direito do mouse no arquivo Explorador de Arquivos
2. Clique em **Propriedades**
3. Selecionar **Desbloquear**
4. Clique **em OK**

Para desbloquear o script usando o PowerShell, consulte [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Depois que o script de atualização de aplicativo offline for baixado, transfira o arquivo para o Salas do Teams dispositivo. Você pode transferir um arquivo para o dispositivo usando uma unidade USB ou acessando o arquivo de um compartilhamento de arquivos de rede enquanto estiver no modo Administração no dispositivo. Lembre-se de observar onde você salva o arquivo no dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Etapa 2: Executar o script para atualizar o Salas do Teams aplicativo

O script de atualização de aplicativo offline precisa ser executado em um prompt de comando com privilégios elevados enquanto o usuário do Skype (o usuário sob o qual o aplicativo é executado) ainda está conectado. Para obter mais informações sobre como fazer logon em uma conta de administrador para usar o prompt de comando com privilégios elevados enquanto o usuário do Skype ainda estiver conectado, consulte Alternar para o modo Administração e voltar quando o aplicativo [Salas do Microsoft Teams falhar](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes).

Faça o seguinte para executar o script em um prompt de comando com privilégios elevados:

1. Alternar para o modo Administração usuário
2. Clique no ícone Iniciar, digite **Prompt de** Comando e selecione **Executar como administrador**
3. Execute o seguinte comando, em `<path to script>` que inclui o caminho completo para o script e o nome do arquivo de script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Por exemplo, se o arquivo de script estiver localizado e `C:\Users\Admin\Downloads`o nome do arquivo de script estiver `MTR-Update-4.5.6.7.ps1`, execute o seguinte comando:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Permitir que o script seja executado. Quando terminar, o script reinicializará o Salas do Teams dispositivo.

Você também pode executar o script usando o PowerShell Remoto. Para obter mais informações sobre como usar o PowerShell remoto com Salas do Teams, consulte [Gerenciamento Remoto usando o PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Etapa 3: Verificar se o aplicativo foi atualizado com êxito

Se o script for executado com êxito, o dispositivo será reinicializado no Salas do Teams aplicativo.

Se o script encontrar um problema, ele indicará qual é o problema na linha de comando e registrará sua saída em um arquivo. Siga as instruções fornecidas pelo script. Se você precisar entrar em contato Suporte da Microsoft, inclua o arquivo de log junto com a solicitação de suporte. O script fornecerá o caminho para o arquivo de log.
