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
description: Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021719"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar a ferramenta de recuperação das Salas do Microsoft Teams

Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte. Essa ferramenta deve ser aplicada quando o console de salas do Microsoft Teams mostra um erro de "configuração do sistema desatualizada" ou antes de executar um botão de ação redefinir a [restauração de fábrica](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Pré-requisitos

Baixe o [pacote de instalação das salas do Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) mais recente e extraia-o em um joystick de memória USB ou compartilhamento de rede acessível ao dispositivo de salas do Microsoft Teams.

> [!NOTE]
> A extração de arquivos do MSI pode ser realizada muitas formas. Qualquer mecanismo que extrai todos os arquivos e preserva a estrutura do diretório é aceitável. Uma dessas formas é usar o comando `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` em que `PathToMsi` representa o caminho completo para o pacote de instalação da sala do Microsoft Teams e `PathToTarget` representa o caminho completo da pasta para a qual você deseja que os arquivos sejam extraídos.

## <a name="running-the-tool"></a>Executar a ferramenta

1) Entre na conta de administrador em seu dispositivo de salas do Microsoft Teams e inicie um prompt de comando elevado.
2) Verifique o dispositivo de salas Microsoft Teams que você pode acessar `RecoveryTool.ps1 file` , que está incluído nos arquivos extraídos do pacote de instalação de salas do Microsoft Teams. O kit pode ser encontrado no compartilhamento de rede ou na unidade USB usada ao preparar pré-requisitos.
3) Executar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Para executar uma restauração de fábrica:
   1. Quando solicitado pelo script, selecione a opção 2: **Redefinir**.
   2. Se o BitLocker estiver ativado, siga as instruções fornecidas no final da saída do script para desabilitá-lo.
   3. Realize a restauração de fábrica.
      1. Abra o aplicativo **configurações** e selecione **Atualizar & segurança**
      2. Navegue até a guia **recuperação** .
      3. Abaixo **restaurar este PC**, selecione **introdução**
      4. Selecione **remover tudo**e, em seguida, **Avançar** e **Redefinir**
        > [!WARNING]
        > O dispositivo de salas do Microsoft Teams pode ficar inutilizável se a opção **manter meus arquivos-remove aplicativos e configurações, mas manter sua opção de arquivos pessoais** estiver selecionada durante o processo de redefinição do Windows. Não selecione esta opção.
      5. O sistema será reiniciado várias vezes. Quando a reinicialização estiver concluída, o sistema estará na tela do Windows "configuração inicial de caixa" (OOBE).



## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
