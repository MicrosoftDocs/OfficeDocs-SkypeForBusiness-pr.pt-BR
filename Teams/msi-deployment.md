---
title: Instalar o Microsoft Teams usando MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Os administradores podem usar o Teams MSI para implantar em massa o Microsoft Teams para usuários ou computadores selecionados.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882034"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar o Microsoft Teams usando MSI
=================================

Para usar o System Center Configuration Manager, a Política de Grupo ou qualquer mecanismo de distribuição de terceiros para ampla implantação, a Microsoft oferece arquivos MSI (de [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa do Teams para usuários ou computadores selecionados. Os administradores podem usar esses arquivos para implantar o Teams remotamente, de modo que os usuários não precisem baixar manualmente o aplicativo Teams. Quando implantado, o Teams iniciará automaticamente para todos os usuários que fizerem login naquela máquina. Recomendamos a implantação do pacote no computador para que todos os novos usuários da máquina também se beneficiem da implantação. 
 
> [!Note] 
> Para saber mais sobre o SCCM, consulte [Introdução ao System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimento de implantação (recomendado)
1. Recupere o pacote mais recente.
2. Use os padrões pré-preenchidos pelo MSI.
3. Implante nos computadores quando possível.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como o pacote Microsoft Teams MSI funciona

O Teams MSI colocará um instalador em Arquivos de Programas. Sempre que um usuário fizer login em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo Teams será instalada na pasta appdata desse usuário. Se o usuário já tiver o aplicativo Teams instalado na pasta appdata, o instalador do MSI ignorará o processo para esse usuário.

Não use o MSI para implantar atualizações, pois o cliente atualizará automaticamente quando detectar que há uma nova versão disponível no serviço. Para reimplantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo. Se você implantar uma versão mais antiga do pacote MSI, o cliente atualizará automaticamente para o usuário quando possível. Se for implantada uma versão muito antiga, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams. 

> [!Important] 
> Não recomendamos mudar os locais de instalação padrão, pois isso pode interromper o fluxo de atualização. Uma versão muito antiga pode impedir que os usuários acessem o serviço. 


## <a name="target-computer-requirements"></a>Requisitos do computador de destino

- .NET framework 4.5 ou posterior
- Windows 7 ou posterior
- 3 GB de espaço em disco para cada perfil de usuário (recomendado)

## <a name="clean-up-and-redeployment-procedure"></a>Procedimento de limpeza e reimplantação
Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI rastreará que o usuário desinstalou o aplicativo Teams e não instalará mais o Teams para esse perfil de usuário. Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:

1. Desinstale o aplicativo Teams instalado para todos os perfis de usuário. 
2. Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\. 
3. Reimplante o pacote MSI no computador específico.

> [!TIP] 
> Você pode usar nosso [Script de limpeza de implantação do Microsoft Teams](.\scripts\Powershell-script-teams-deployment-clean-up.md) via SCCM para concluir as etapas 1 e 2.                              

