---
title: Instalar usando o MSI Teams da Microsoft
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Os administradores podem usar o MSI equipes para em massa implantar Teams da Microsoft para selecionar usuários ou computadores.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882034"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar usando o MSI Teams da Microsoft
=================================

Para usar o System Center Configuration Manager ou política de grupo ou qualquer mecanismos de distribuição de terceiros para implantação em larga escala, a Microsoft forneceu arquivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa de equipes para selecionar os usuários ou computadores. Os administradores podem usar esses arquivos para implantar remotamente equipes para que os usuários não precisam baixar manualmente o aplicativo de equipes. Quando implantado, equipes gerará automaticamente lançamento para todos os usuários que entram nesta máquina. Recomendamos que você implante o pacote para o computador, para que todos os novos usuários do computador também serão beneficiados com essa implantação. 
 
> [!Note] 
> Para saber mais sobre SCCM, consulte [Introdução para o System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimento de implantação (recomendado)
1. Recupere o pacote mais recente.
2. Use os padrões pré-preenchido pelo MSI.
3. Implante em computadores quando possível.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como funciona ao pacote MSI de equipes da Microsoft

O MSI equipes colocará um instalador em arquivos de programa. Sempre que um usuário se conecta em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo equipes será instalada na pasta de appdata desse usuário. Se um usuário já tiver o aplicativo de equipes instalado na pasta appdata, o instalador MSI irá ignorar o processo para esse usuário.

Não use o MSI para implantar atualizações, pois o cliente irá atualizar automaticamente quando detecta que uma nova versão é disponibilizada pelo serviço. Para reimplantar o instalador mais recente use o processo de reimplantando MSI descrito abaixo. Se você implantar uma versão mais antiga do pacote do MSI, o cliente será atualizado automaticamente sempre que possível para o usuário. Se uma versão antiga muito obtém implantada, o MSI irá disparar uma atualização do aplicativo antes que o usuário seja capaz de usar equipes. 

> [!Important] 
> Não recomendamos que você altere os locais de instalação padrão, como isso poderia quebrará o fluxo de atualização. Ter uma versão antiga muito eventualmente bloqueará os usuários acessem o serviço. 


## <a name="target-computer-requirements"></a>Requisitos do computador de destino

- .NET framework 4.5 ou posterior
- Windows 7 ou posterior
- 3 GB de espaço em disco para cada perfil de usuário (recomendado)

## <a name="clean-up-and-redeployment-procedure"></a>Limpeza e o procedimento de reimplantação
Se um usuário desinstala equipes de seu perfil de usuário, o instalador MSI irá controlar que o usuário tiver desinstalado o aplicativo de equipes e não são mais instalar equipes para esse perfil de usuário. Para reimplantar equipes para esse usuário em um computador particular, onde ele foi desinstalado, faça o seguinte:

1. Desinstale o aplicativo de equipes instalado para cada perfil de usuário. 
2. Após a desinstalação, exclua o diretório recursivamente em % localappdata%\Microsoft\Teams\. 
3. Reimplante o pacote MSI nesse computador específico.

> [!TIP] 
> Você pode usar o nosso script de [implantação de equipes da Microsoft limpar](.\scripts\Powershell-script-teams-deployment-clean-up.md) para realizar as etapas 1 e 2 por meio do SCCM.                              

