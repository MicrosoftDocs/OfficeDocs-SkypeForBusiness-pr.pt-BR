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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Este artigo discute como usar a ferramenta de recuperação para Salas do Microsoft Teams, que você usaria para colocar um sistema desatualizados em um estado com suporte.
ms.openlocfilehash: 70b2d199c4fe13138e2f46fd0b49e95efbd18e9c
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706160"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar a ferramenta de recuperação das Salas do Microsoft Teams

Este artigo discute como usar a ferramenta de recuperação para Salas do Microsoft Teams, que você usaria para colocar um sistema desatualizados em um estado com suporte. Essa ferramenta deve ser aplicada quando o console Salas do Microsoft Teams mostrar um erro de "configuração do sistema desatualizada" ou antes de executar uma restauração de fábrica de redefinição de fábrica do botão [de push](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Pré-requisitos

Baixe o pacote de [instalação Salas do Microsoft Teams e](https://go.microsoft.com/fwlink/?linkid=851168) extraia-o para um pen drive ou compartilhamento de rede acessível para Salas do Microsoft Teams.

> [!NOTE]
> A extração dos arquivos da MSI pode ser realizada por vários meios. Qualquer mecanismo que extraia todos os arquivos e preserva sua estrutura de diretório é aceitável. Uma maneira é `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` usar o comando em que representa o caminho completo para o pacote de instalação do Salas do Microsoft Teams e representa o caminho completo para a `PathToTarget` pasta para a qual você deseja extrair os arquivos.

## <a name="running-the-tool"></a>Executando a ferramenta

1) Entre na conta de administrador em seu Salas do Microsoft Teams e inicie um prompt de comando com privilégios elevados.
2) Verifique no Salas do Microsoft Teams que `RecoveryTool.ps1` você pode acessar o arquivo, que está incluído nos arquivos extraídos do pacote de instalação Salas do Microsoft Teams aplicativo. O kit pode ser encontrado no compartilhamento de rede ou na unidade USB usada ao preparar os pré-requisitos.
3) Executar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Para executar uma restauração de fábrica:
   1. Quando solicitado pelo script, selecione a opção 2: **Redefinir**.
   2. Se o BitLocker estiver ativado, siga as instruções fornecidas no final da saída do script para desabilitá-lo.
   3. Execute a restauração de fábrica.
      1. Abra o **aplicativo Configurações** e selecione **Atualizar & Segurança**
      2. Navegue até a **guia Recuperação** .
      3. Abaixo **de Redefinir este computador**, selecione **Introdução**
      4. Selecione **Remover tudo** e, em **seguida, Avançar** e **Redefinir**
        > [!WARNING]
        > O Salas do Microsoft Teams dispositivo poderá se tornar inutilizável se a opção Manter meus arquivos – Remover **aplicativos** e configurações, mas manter sua opção de arquivos pessoais estiver selecionada durante o processo de Redefinição do Windows. Não selecione essa opção.
      5. O sistema será reinicializado várias vezes. Quando a redefinição for concluída, o sistema estará na tela "experiência inicial" (OOBE) do Windows.



## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
