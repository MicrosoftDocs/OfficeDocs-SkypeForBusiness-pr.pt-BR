---
title: Implantar equipes em escala para trabalhadores de linha de frente no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como implantar equipes em escala para os trabalhadores da linha de frente em sua organização.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947221"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Implantar equipes em escala para trabalhadores de linha de frente no Microsoft Teams

> [!NOTE]
> Esse recurso está atualmente em versão prévia privada. Se você quiser participar da versão prévia privada, entre em contato [conosco em dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Visão Geral
 
Sua organização pode ter muitas equipes que você usa para impulsionar a comunicação e a colaboração entre sua força de trabalho de linha de frente, que estão distribuídas em diferentes lojas, locais e funções. Atualmente, não há uma solução fácil para implantar, configurar e gerenciar essas equipes e usuários em escala.

Estamos criando uma solução para permitir que os administradores implantem e gerenciem equipes em escala.

Aqui está uma visão geral dos recursos disponíveis hoje para criar e gerenciar um grande número de equipes por vez e o que estamos planejando para o futuro próximo.

||Disponível hoje |Posteriormente em 2022  |
|---------|---------|---------|
|**Número de equipes que você pode criar por lote**|Até 100 |Até 500|
|**Número de usuários que você pode adicionar por equipe**|Até 25|Até 25|

A implantação de equipes em escala permite que você:

- Crie equipes usando modelos pré-criados ou seus próprios modelos personalizados.
- Adicione usuários às equipes como proprietários ou membros.
- Gerencie equipes em escala adicionando ou removendo usuários de equipes existentes.
- Mantenha-se notificado por email, incluindo conclusão, status e erros (se houver). Os proprietários e membros da equipe são notificados.

## <a name="how-to-deploy-teams-at-scale"></a>Como implantar equipes em escala

> [!NOTE]
> Antes de implantar suas equipes, verifique se todos os proprietários de equipes têm uma licença do Teams.

Siga estas etapas para implantar um grande número de equipes por vez.

Use o ```New-CsBatchTeamsDeployment``` cmdlet para enviar um lote de equipes a serem criados. Uma ID de orquestração é gerada para cada lote. Em seguida, você pode usar o ```Get-CsBatchTeamsDeployment``` cmdlet para acompanhar o progresso e o status de cada lote.

1. Instale o PowerShell versão 7 ou posterior. Para obter diretrizes passo a passo, consulte [Instalar o PowerShell no Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Execute o PowerShell no modo de administrador.
1. Execute o seguinte para desinstalar qualquer módulo do PowerShell do Teams instalado anteriormente.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Se você receber uma mensagem de erro, já estará definido. Vá para a próxima etapa.
1. Baixe e instale a [versão mais recente do módulo PowerShell do Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Execute o seguinte para se conectar ao Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Quando for solicitado, entre usando suas credenciais de administrador.

1. Execute o seguinte para obter uma lista dos comandos no módulo do PowerShell do Teams.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Verifique se e ```New-CsBatchTeamsDeployment``` estão ```Get-CsBatchTeamsDeployment``` listados.

1. Execute o seguinte para implantar um lote de equipes. Você pode inserir até cinco endereços de email no **parâmetro UsersToNotify** .

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. Execute o seguinte para verificar o status do lote enviado.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Nos envie seus comentários

Nós damos valor aos seus comentários. Usabilidade, confiabilidade, desempenho,&mdash;demos as boas-vindas a tudo!

Envie [dscale@microsoft.com](mailto:dscale@microsoft.com) email e inclua sua ID de orquestração e o arquivo de erro, se você tiver.

## <a name="related-articles"></a>Artigos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
