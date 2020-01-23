---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte.
ms.openlocfilehash: 3a62256a5e39d93033588ca2be779e9c3b76a4f5
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268729"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar a ferramenta de recuperação das Salas do Microsoft Teams

Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte. Essa ferramenta deve ser aplicada quando o console de salas do Microsoft Teams mostra um erro de "configuração do sistema desatualizada" ou antes de executar um botão de ação redefinir a [restauração de fábrica](https://docs.microsoft.com/microsoftteams/room-systems/rooms-operations#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Pré-requisitos

Baixe o [pacote de instalação das salas do Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) mais recente e extraia-o em um joystick de memória USB ou compartilhamento de rede acessível ao dispositivo de salas do Microsoft Teams.

> [!NOTE]
> A extração de arquivos do MSI pode ser realizada muitas formas. Qualquer mecanismo que extrai todos os arquivos e preserva a estrutura do diretório é aceitável. Uma dessas formas é usar o comando `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` em que `PathToMsi` representa o caminho completo para o pacote de instalação da sala do Microsoft `PathToTarget` Teams e representa o caminho completo da pasta para a qual você deseja que os arquivos sejam extraídos.

## <a name="running-the-tool"></a>Executar a ferramenta

1) Entre na conta de administrador em seu dispositivo de salas do Microsoft Teams e inicie um prompt de comando elevado.
2) Verifique o dispositivo de salas Microsoft Teams que você pode acessar `RecoveryTool.ps1 file`, que está incluído nos arquivos extraídos do pacote de instalação de salas do Microsoft Teams. O kit pode ser encontrado no compartilhamento de rede ou na unidade USB usada ao preparar pré-requisitos.
3) Executar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Se você estiver executando uma restauração de fábrica:
   - Quando solicitado pelo script, selecione a opção 2: **Redefinir**.
   - Se o BitLocker estiver ativado, siga as instruções fornecidas no final da saída do script para desabilitá-lo.
   - Realize a restauração de fábrica.
      - Abra o aplicativo **configurações** e selecione **Atualizar & segurança**
      - Navegue até a guia **recuperação** .
      - Abaixo **restaurar este PC**, selecione **introdução**
      - Selecione **remover tudo**e, em seguida, **Avançar** e **Redefinir**
      - O sistema será reiniciado várias vezes. Quando a reinicialização estiver concluída, o sistema estará na tela OOBE do Windows.
5) Se você estiver reparando um sistema "desatualizado":
    - Quando solicitado pelo script, selecione a opção 1: **reparar**.
    - Após a conclusão, reinicie o dispositivo de salas do Microsoft Teams. Ele reiniciará novamente automaticamente e a recuperação será completada na segunda vez.

> [!NOTE]
> Há um problema conhecido em que as salas do Microsoft Teams podem ficar inúteis se a opção **manter meus arquivos-remove meus arquivos-remove aplicativos e configurações, mas mantém a opção arquivos pessoais** selecionada durante o processo de redefinição do Windows. Não *Use essa* opção.

## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
