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
description: Este artigo aborda como usar a ferramenta de recuperação de Salas do Microsoft Teams, que você usaria para trazer um sistema desa atualizado para um estado com suporte.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021719"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar a ferramenta de recuperação das Salas do Microsoft Teams

Este artigo aborda como usar a ferramenta de recuperação de Salas do Microsoft Teams, que você usaria para trazer um sistema desa atualizado para um estado com suporte. Essa ferramenta deve ser aplicada quando o console salas do Microsoft Teams mostrar um erro "configuração do sistema des des date" ou antes de executar uma restauração de fábrica de restauração de botão [de push.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Pré-requisitos

Baixe o pacote [de instalação mais recente do Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) e extraia-o para um cartão de memória USB ou compartilhamento de rede acessível para o dispositivo Salas do Microsoft Teams.

> [!NOTE]
> Extrair os arquivos do MSI pode ser realizado de várias maneiras. Qualquer mecanismo que extraia todos os arquivos e preserve sua estrutura de diretórios é aceitável. Uma delas é usar o comando onde representa o caminho completo para o pacote de instalação da Sala do Microsoft Teams e representa o caminho completo para a pasta para a qual você gostaria que os arquivos fosse `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` extraídos.

## <a name="running-the-tool"></a>Executando a ferramenta

1) Entre na conta de administrador em seu dispositivo Salas do Microsoft Teams e iniciar um prompt de comando elevado.
2) Verifique no dispositivo Salas do Microsoft Teams que você pode acessar, que está incluído nos arquivos extraídos do pacote de instalação salas `RecoveryTool.ps1 file` do Microsoft Teams. O kit pode ser encontrado no compartilhamento de rede ou unidade USB usada durante a preparação de pré-requisitos.
3) `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`Executar.
4) Para executar uma restauração de fábrica:
   1. Quando solicitado pelo script, selecione a opção 2: **Redefinir.**
   2. Se o BitLocker estiver on, siga as instruções fornecidas no final da saída do script para desabilitá-lo.
   3. Executar a restauração de fábrica.
      1. Abra o **aplicativo Configurações** e selecione **Atualizar & Segurança**
      2. Navegue até a **guia Recuperação.**
      3. Beneath **Reset this PC,** select **Get started**
      4. Selecione **Remover tudo** e, em **seguida, Próximo** e **Redefinir**
        > [!WARNING]
        > O dispositivo Salas do Microsoft Teams pode se tornar inutilizável se o arquivo Manter meus arquivos **– remove aplicativos** e configurações, mas mantém sua opção de arquivos pessoais selecionada durante o processo de Redefinição do Windows. Não selecione essa opção.
      5. O sistema será reiniciado várias vezes. Quando a redefinição for concluída, o sistema estará na tela "experiência fora da caixa" (OOBE) do Windows.



## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
