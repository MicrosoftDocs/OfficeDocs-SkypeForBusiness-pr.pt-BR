---
title: Instalar o Microsoft Teams usando MSI por meio do Gerenciador de configuração do Microsoft Endpoint
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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f57eeb44fd728d1b656ce13f56cf2c5997805b9
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888360"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Instalar o Microsoft Teams usando o Gerenciador de configuração do Microsoft Endpoint

> [!Tip]
> Assista à sessão a seguir para conhecer os benefícios do Windows Desktop Client e como planejar e executar sua implantação: [Cliente de Desktop do Microsoft Teams](https://aka.ms/teams-clients)

Para usar o Gerenciador de configuração do Microsoft Endpoint ou a política de grupo ou qualquer mecanismo de distribuição de terceiros para implantação ampla, a Microsoft forneceu arquivos MSI (32 bits e 64 bits) que os administradores podem usar para a implantação em massa do teams para selecionar usuários ou computadores. Os administradores podem usar esses arquivos para implantar o Teams remotamente, de modo que os usuários não precisem baixar manualmente o aplicativo Teams. Quando implantado, o Teams iniciará automaticamente para todos os usuários que fizerem logon naquele computador. (Você pode desabilitar o início automático depois de instalar o aplicativo. [Confira abaixo](#disable-auto-launch-for-the-msi-installer).) É recomendável implantar o pacote no computador para que todos os novos usuários dele também se beneficiem com a implantação.

Estes são os links para os arquivos MSI:


|Entity  |32 bit      |64 bit      |
|---------|---------|---------|
|Empresas     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Governo Federal-GCC     | [32 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Governo Federal-GCC alto    | [32 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Governo Federal-DoD     | [32 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

O Teams também pode ser incluído em uma implantação do Office 365 ProPlus. Para obter mais informações, confira [Implantar o Microsoft Teams com Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Para saber mais sobre o Gerenciador de configuração do Microsoft EndPoint, consulte [o que é o Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimento de implantação (recomendado)

1. Recupere o pacote mais recente.
2. Use os padrões pré-preenchidos pelo MSI.
3. Implante nos computadores quando possível.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como o pacote Microsoft Teams MSI funciona

### <a name="pc-installation"></a>Instalação no PC

O Teams MSI colocará um instalador em Arquivos de Programas. Sempre que um usuário fizer logon em um novo perfil de usuário do Windows, o instalador será iniciado, e uma cópia do aplicativo Teams será instalada na pasta appdata desse usuário. Se o usuário já tiver o aplicativo Teams instalado na pasta appdata, o instalador do MSI ignorará o processo para esse usuário.

Não use o MSI para implantar atualizações, pois o cliente atualizará automaticamente quando detectar que há uma nova versão disponível no serviço. Para reimplantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.Se você implantar uma versão mais antiga do pacote MSI, o cliente atualizará automaticamente (exceto em ambientes da VDI) para o usuário quando possível. Se uma versão muito antiga for implantada, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams.

> [!Important]
> Não recomendamos mudar os locais de instalação padrão, pois isso pode interromper o fluxo de atualização. Uma versão muito antiga pode impedir que os usuários acessem o serviço.

#### <a name="target-computer-requirements"></a>Requisitos do computador de destino

- .NET framework 4.5 ou posterior
- Windows 7 ou posterior
- Windows Server 2012 R2 ou posterior
- 3 GB de espaço em disco para cada perfil de usuário (recomendado)

### <a name="vdi-installation"></a>Instalação da VDI

Para obter uma orientação completa sobre como implantar o aplicativo da área de trabalho Teams no VDI, consulte [Teams para infraestrutura de área de trabalho virtualizada](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedimento de limpeza e reimplantação

Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI rastreará que o usuário desinstalou o aplicativo Teams e não instalará mais o Teams para esse perfil de usuário. Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:

1. Desinstale o aplicativo Teams instalado para todos os perfis de usuário.
2. Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\.
3. Reimplante o pacote MSI no computador específico.

> [!TIP]
> Você pode usar o script de [limpeza de implantação do Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para executar as etapas 1 e 2 via Configuration Manager.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impedir que o Microsoft Teams inicie automaticamente após a instalação

O comportamento padrão do MSI é instalar o aplicativo Teams assim que um usuário entrar e iniciar automaticamente o Microsoft Teams. Se não quiser que as equipes iniciem automaticamente para os usuários após a instalação, você pode usar a política de grupo para definir uma configuração de política ou desabilitar o início automático para o instalador MSI.

#### <a name="use-group-policy-recommended"></a>Usar política de grupo (recomendado)

Habilite a configuração **impedir que o Microsoft Teams seja iniciado automaticamente após a instalação** da política de grupo. Você pode encontrar essa configuração de política nas equipes do usuário Templates\Microsoft de configuração do usuário. Esse é o método recomendado porque você pode desativar ou ativar a configuração de política de acordo com as necessidades da sua organização.

Quando você habilitar essa configuração de política antes de instalar o Microsoft Teams, o Teams não iniciará automaticamente quando os usuários fizerem logon no Windows. Após o usuário entrar no Microsoft Teams pela primeira vez, o Teams é iniciado automaticamente na próxima vez que o usuário faz logon.

Para saber mais, consulte [usar a política de grupo para impedir que o Microsoft Teams inicie automaticamente após a instalação](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Se você já implantou o Microsoft Teams e quer definir essa política para desabilitar o AutoStart do Teams, primeiro defina a configuração da política de grupo com o valor desejado e execute o script do Microsoft [AutoStart Reset](scripts/powershell-script-teams-reset-autostart.md) para cada usuário.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Desabilitar o início automático do instalador MSI

Você pode desabilitar o início automático para o instalador MSI usando o parâmetro **Options = "noAutoStart = true"** da seguinte maneira.  

Para a versão de 32 bits

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

Para a versão de 64 bits

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

Quando um usuário faz logon no Windows, o Microsoft Teams é instalado com o MSI e um atalho para iniciar o Teams é adicionado à área de trabalho do usuário. O Microsoft Teams não começará até que o usuário inicie manualmente o Teams. Após o usuário iniciar manualmente o Teams, o Teams é iniciado automaticamente sempre que o usuário faz logon.

> [!Note]
> Se executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas. Mesmo que você o execute como administrador, sem executá-lo com permissões elevadas, o instalador não poderá configurar a opção de desabilitar o início automático.
