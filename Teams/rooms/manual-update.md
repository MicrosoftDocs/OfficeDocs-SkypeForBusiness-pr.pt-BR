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
description: Saiba como atualizar manualmente o dispositivo salas do Microsoft Teams para uma versão específica.
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117509"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Atualizar manualmente um dispositivo salas do Microsoft Teams

O aplicativo Salas do Microsoft Teams é distribuído por meio da Microsoft Store. As atualizações do aplicativo são instaladas automaticamente na Microsoft Store durante a manutenção noturna; este é o método recomendado para obter atualizações. No entanto, há algumas situações em que um dispositivo salas do Teams não pode receber atualizações da Microsoft Store. Por exemplo, as políticas de segurança podem não permitir que os dispositivos se conectem à Internet ou podem não permitir que os aplicativos sejam baixados da Microsoft Store. Ou talvez você queira atualizar um dispositivo antes de executar a instalação, durante o qual a Microsoft Store não está disponível.

Se você não conseguir obter atualizações da Microsoft Store, poderá usar um script do PowerShell de atualização de aplicativo offline para atualizar manualmente seus dispositivos salas do Teams para uma versão mais recente do aplicativo Salas do Teams. Siga as etapas deste artigo para atualizar manualmente seus dispositivos salas do Teams.

> [!NOTE]
> Esse processo só pode atualizar um dispositivo salas do Teams com o aplicativo Salas do Teams já instalado. Ele não pode ser usado para executar uma nova instalação. Ele também não pode ser usado para fazer o downgrade do aplicativo para uma versão mais antiga. Para executar uma nova instalação do aplicativo Salas do Teams, entre em contato com o fabricante do dispositivo para mídia específica a ele ou consulte Preparar a [mídia de instalação.](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Etapa 1: Baixar o script de atualização de aplicativo offline

Primeiro, baixe a versão mais recente do script de atualização do aplicativo offline. Para baixar o script, clique em <https://go.microsoft.com/fwlink/?linkid=2151817> . O script será baixado para a pasta de downloads padrão em seu dispositivo.

Os arquivos baixados podem ser marcados como bloqueados pelo Windows. Se você precisar executar o script sem nenhuma interação, será necessário desbloquear o script. Para desbloquear o script, faça o seguinte:

1. Clique com o botão direito do mouse no arquivo no Explorador de Arquivos
2. Clique **em Propriedades**
3. Selecionar **Desbloquear**
4. Clique **em OK**

Para desbloquear o script usando o PowerShell, consulte [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Depois que o script de atualização de aplicativo offline for baixado, transfira o arquivo para o dispositivo Salas do Teams. Você pode transferir um arquivo para o dispositivo usando uma unidade USB ou acessando o arquivo de um compartilhamento de arquivos de rede enquanto estiver no Modo De Administração no dispositivo. Lembre-se de observar onde você salva o arquivo no dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Etapa 2: Executar o script para atualizar o aplicativo Salas do Teams

O script de atualização de aplicativo offline precisa ser executado a partir de um prompt de comando elevado enquanto o usuário do Skype (o usuário sob o qual o aplicativo é executado) ainda está assinado. Para obter mais informações sobre como fazer logon em uma conta de administrador para usar o prompt de comando com privilégios elevados enquanto o usuário do Skype ainda estiver conectado, consulte [Alternando](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)para o Modo de Administração e de volta quando o aplicativo salas do Microsoft Teams estiver em execução .

Faça o seguinte para executar o script de um prompt de comando elevado:

1. Alternar para o Modo de Administração
2. Clique no ícone Iniciar, digite **Prompt de** Comando e selecione Executar **como administrador**
3. Execute o seguinte comando onde inclui o caminho completo para o script e `<path to script>` o nome do arquivo de script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Por exemplo, se o arquivo de script estiver localizado em , e o nome do `C:\Users\Admin\Downloads` arquivo de script for , execute o seguinte `MTR-Update-4.5.6.7.ps1` comando:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Permitir que o script seja executado. Quando terminar, o script reiniciará o dispositivo Salas do Teams.

Você também pode executar o script usando o PowerShell Remoto. Para obter mais informações sobre como usar o PowerShell Remoto com dispositivos salas do Teams, consulte [Gerenciamento Remoto usando o PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Etapa 3: Verificar se o aplicativo foi atualizado com êxito

Se o script for executado com êxito, o dispositivo será reiniciado no aplicativo Salas do Teams.

Se o script encontrar um problema, ele indicará qual é o problema na linha de comando e registrará sua saída em um arquivo. Siga todas as instruções fornecidas pelo script. Se precisar entrar em contato com o Suporte da Microsoft, certifique-se de incluir o arquivo de log juntamente com a solicitação de suporte. O script fornecerá o caminho para o arquivo de log.