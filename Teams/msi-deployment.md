---
title: Instalar o Microsoft Teams usando MSI via SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Os administradores podem usar o Teams MSI para implantar em massa o Microsoft Teams para usuários ou computadores selecionados.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e2354c28916af3c1c0be47848ee7bd2a72bf278
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238662"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar o Microsoft Teams usando MSI
=================================

> [!Tip]
> Assista à sessão a seguir para conhecer os benefícios do Windows Desktop Client e como planejar e executar sua implantação: [Cliente de Desktop do Microsoft Teams](https://aka.ms/teams-clients)

Para usar o System Center Configuration Manager, a Política de Grupo ou qualquer mecanismo de distribuição de terceiros para ampla implantação, a Microsoft oferece arquivos MSI (de [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa do Teams para usuários ou computadores selecionados. Os administradores podem usar esses arquivos para implantar o Teams remotamente, de modo que os usuários não precisem baixar manualmente o aplicativo Teams. Quando implantado, o Teams iniciará automaticamente para todos os usuários que fizerem login naquele computador. (Você pode desabilitar o início automático depois de instalar o aplicativo. [Confira abaixo](#disable-auto-launch-for-the-msi-installer).) É recomendável implantar o pacote no computador para que todos os novos usuários dele também se beneficiem com a implantação. 

O Teams também pode ser incluído em uma implantação do Office 365 ProPlus. Para obter mais informações, confira [Implantar o Microsoft Teams com Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).
 
> [!Note] 
> Para saber mais sobre o SCCM, confira [Introdução ao System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimento de implantação (recomendado)
1. Recupere o pacote mais recente.
2. Use os padrões pré-preenchidos pelo MSI.
3. Implante nos computadores quando possível.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como o pacote Microsoft Teams MSI funciona

### <a name="pc-installation"></a>Instalação no PC

> [!Note] 
> Confira [Instalação da VDI](#vdi-installation) para obter instruções sobre como implantar o Teams em um ambiente de Virtual Desktop Infrastructure (VDI).

O Teams MSI colocará um instalador em Arquivos de Programas. Sempre que um usuário fizer login em um novo perfil de usuário do Windows, o instalador será iniciado, e uma cópia do aplicativo Teams será instalada na pasta appdata desse usuário. Se o usuário já tiver o aplicativo Teams instalado na pasta appdata, o instalador do MSI ignorará o processo para esse usuário.

Não use o MSI para implantar atualizações, pois o cliente atualizará automaticamente quando detectar que há uma nova versão disponível no serviço. Para reimplantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.Se você implantar uma versão mais antiga do pacote MSI, o cliente atualizará automaticamente (exceto em ambientes da VDI) para o usuário quando possível. Se uma versão muito antiga for implantada, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams. 

> [!Important] 
> Não recomendamos mudar os locais de instalação padrão, pois isso pode interromper o fluxo de atualização. Uma versão muito antiga pode impedir que os usuários acessem o serviço. 

#### <a name="target-computer-requirements"></a>Requisitos do computador de destino

- .NET framework 4.5 ou posterior
- Windows 7 ou posterior
- 3 GB de espaço em disco para cada perfil de usuário (recomendado)

### <a name="vdi-installation"></a>Instalação da VDI

Este é o processo de implantação do aplicativo de área de trabalho do Teams. Para obter instruções completas, confira [Teams para Virtual Desktop Infrastructure](teams-for-vdi.md).

1. Baixe o pacote MSI do Teams usando um dos seguintes links, dependendo do ambiente. Recomendamos a versão de 64 bits de uma máquina virtual (VM) da VDI com um sistema operacional de 64 bits.

    - [Versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [Versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Execute o seguinte comando para instalar o MSI na VM da VDI (ou conclua a atualização).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Isso instala o Teams em Arquivos de Programas. Nesse ponto, a configuração da imagem dourada está concluída.

    A próxima sessão de logon interativo inicia o Teams e pede credenciais. Lembre-se de que não é possível desativar o início automático do Teams ao instalá-lo na VDI usando a propriedade ALLUSER.

3. Execute o comando a seguir para desinstalar o MSI na VM da VDI (ou preparar para atualizá-lo).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Isso desinstala o Teams do Arquivos de Programas.

## <a name="clean-up-and-redeployment-procedure"></a>Procedimento de limpeza e reimplantação

Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI rastreará que o usuário desinstalou o aplicativo Teams e não instalará mais o Teams para esse perfil de usuário. Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:

1. Desinstale o aplicativo Teams instalado para todos os perfis de usuário. 
2. Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\.
3. Reimplante o pacote MSI no computador específico.

> [!TIP] 
> Você pode usar nosso script de [Limpeza de implantação do Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para concluir as etapas 1 e 2 via SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Desabilitar o início automático do instalador MSI

O comportamento padrão do MSI é instalar o cliente do Teams assim que um usuário entrar e iniciá-lo automaticamente. Você pode modificar esse comportamento com os parâmetros abaixo desta maneira:

- Quando um usuário fizer logon no Windows, as equipes serão instaladas com o MSI
- No entanto, o cliente do Teams não será iniciado até que o usuário o tenha iniciado manualmente
- Um atalho para iniciar o Teams será adicionado à área de trabalho do usuário
- Uma vez iniciado manualmente, o Teams será iniciado automaticamente sempre que o usuário fizer logon

Para a versão de 32 bits
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Para a versão de 64 bits
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Se executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas. Mesmo que você o execute como administrador, se isso não for feito com permissões elevadas, o instalador não poderá configurar a opção para desabilitar o início automático.
