---
title: Instalar usando o MSI Teams da Microsoft
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Os administradores podem usar o MSI equipes para em massa implantar Teams da Microsoft para selecionar usuários ou computadores.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a>Instalar usando o MSI Teams da Microsoft
===========================================

Para aproveitar o System Center Configuration Manager ou política de grupo ou qualquer 3º mecanismos de distribuição de terceiros para implantação em larga escala, a Microsoft forneceu arquivos MSI ( [32 bits](http://aka.ms/teams32bitmsi) e [64 bits](http://aka.ms/teams64bitmsi)) para os administradores aproveitar durante a implantação em massa da Microsoft Teams para selecionar usuários ou máquinas. Os administradores podem usar esses arquivos para implantar remotamente equipes para que os usuários não precisam baixar manualmente o aplicativo de equipes. Quando implantado, equipes gerará automaticamente lançamento para todos os usuários que entrar nesta máquina. É recomendável que você implante o pacote para a máquina, para que todos os novos usuários para as máquinas também serão beneficiados com essa implantação. 
 
> [!Note] 
> Para saber mais sobre SCCM, consulte. [Introdução para o System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a>Procedimento de implantação (recomendações)
1. Recuperar o último pacote
2. Use os padrões pré-preenchido pelo MSI
3. Implantar máquinas quando possível

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como funciona ao pacote MSI de equipes da Microsoft

O MSI equipes colocará um instalador em arquivos de programa. Sempre que um usuário se conecta em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo de equipes será instalada na pasta de appdata desse usuário. Se um usuário já tiver o aplicativo de equipes instalado na pasta appdata, o instalador MSI irá ignorar o processo para esse usuário.

Não utilizam o MSI para implantar atualizações, o cliente irá atualizar automaticamente quando detecta que uma nova versão é disponibilizada pelo serviço. Para reimplantar o instalador mais recente use o processo de reimplantando MSI descrito abaixo. Se você implantar uma versão mais antiga do pacote do MSI, o cliente será atualizado automaticamente sempre que possível para o usuário. Se uma versão antiga muito obtém implantada, o MSI irá disparar uma atualização do aplicativo antes que o usuário seja capaz de usar equipes. 

> [!Important] 
> Não é recomendável que você alterar qualquer localizações de instalação, como isso o fluxo de atualização pode ser desfeito. Que então eventualmente bloqueará os usuários acessem o serviço. 


## <a name="target-machine-requirements"></a>Requisitos de máquina de destino:

1. .NET framework 4.5 ou posterior
2. Windows 7 ou posterior
2. 32GB de espaço em disco para cada perfil de usuário (recomendado)

## <a name="clean-upredeployment-procedure"></a>Limpar up\redeployment procedimento
Se um usuário desinstala equipes a partir do seu perfil de usuário, o instalador MSI irá controlar que o usuário tiver desinstalado o aplicativo de equipes e não são mais instalar equipes para esse perfil de usuário. Para reimplantar equipes para esse usuário em uma máquina específica, onde ele foi desinstalado, você precisará:

1. Desinstalar o aplicativo de equipes instalado para cada perfil de usuário 
2. Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\ 
3. Reimplantar o pacote MSI àquela máquina específica

> [!TIP] 
> Você pode aproveitar o nosso script de [implantação de equipes da Microsoft limpar](.\scripts\Powershell-script-teams-deployment-clean-up.md) para realizar esta etapa 1 e 2 por meio do SCCM.                                

