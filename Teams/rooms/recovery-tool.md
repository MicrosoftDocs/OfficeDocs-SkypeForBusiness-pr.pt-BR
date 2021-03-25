---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo discute como usar a ferramenta de recuperação para Salas do Microsoft Teams, que você usaria para colocar um sistema desaparado em um estado com suporte.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117489"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar a ferramenta de recuperação das Salas do Microsoft Teams

Este artigo discute como usar a ferramenta de recuperação para Salas do Microsoft Teams, que você usaria para colocar um sistema desaparado em um estado com suporte. Essa ferramenta deve ser aplicada quando o console das Salas do Microsoft Teams mostrar um erro de "configuração do sistema desconheçada" ou antes de executar uma restauração de fábrica de redefinição de fábrica do botão de [push.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Pré-requisitos

Baixe o pacote de instalação mais recente do [Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) e extraia-o para um pen drive ou compartilhamento de rede acessível para o dispositivo salas do Microsoft Teams.

> [!NOTE]
> Extrair os arquivos do MSI pode ser realizado por vários meios. Qualquer mecanismo que extraia todos os arquivos e preserva sua estrutura de diretórios é aceitável. Uma dessas maneira é usar o comando onde representa o caminho completo para o pacote de instalação da Sala do Microsoft Teams e representa o caminho completo para a pasta à qual você gostaria que os arquivos `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` extraídos.

## <a name="running-the-tool"></a>Executando a ferramenta

1) Entre na conta de administrador no dispositivo salas do Microsoft Teams e iniciar um prompt de comando com privilégios elevados.
2) Verifique no dispositivo salas do Microsoft Teams que você pode acessar o , que está incluído nos arquivos extraídos do pacote de instalação do `RecoveryTool.ps1 file` Microsoft Teams Rooms. O kit pode ser encontrado no compartilhamento de rede ou unidade USB usado na preparação de pré-requisitos.
3) Executar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Para executar uma restauração de fábrica:
   1. Quando solicitado pelo script, selecione a opção 2: **Redefinir**.
   2. Se o BitLocker estiver em, siga as instruções fornecidas no final da saída do script para desabilitá-lo.
   3. Execute a restauração de fábrica.
      1. Abra o **aplicativo Configurações** e selecione **Atualizar & Segurança**
      2. Navegue até a **guia Recuperação.**
      3. Abaixo **redefinir este computador,** selecione **Começar**
      4. Selecione **Remover tudo** e, em **seguida, Next** e **Reset**
        > [!WARNING]
        > O dispositivo salas do Microsoft Teams pode se tornar inutilizável se a opção Manter meus arquivos **- Remove Aplicativos** e configurações, mas mantém sua opção de arquivos pessoais selecionada durante o processo de Redefinição do Windows. Não selecione essa opção.
      5. O sistema será reiniciado várias vezes. Quando a redefinição for concluída, o sistema estará na tela "experiência fora da caixa" (OOBE) do Windows.



## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)