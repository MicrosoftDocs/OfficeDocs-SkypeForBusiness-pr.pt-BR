---
title: Instalação em massa Teams usando Windows Instalador (MSI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Use Windows arquivos MSI (Instalador) para distribuir o cliente Teams para vários usuários e computadores.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fc9e17f958b1770573cf6729ef6aca9b22ffe03d
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893560"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>Instalação em massa Teams usando Windows Instalador (MSI)

> [!Tip]
> Assista à sessão a seguir para aprender sobre os benefícios do Cliente de Área de trabalho Windows, como planejá-lo e como implantá-lo[: o Teams do Cliente de área de trabalho Windows](https://aka.ms/teams-clients).

A Microsoft fornece arquivos MSI de 32 bits, 64 bits e ARM64 que você pode usar para implantar em massa Microsoft Teams selecionar usuários e computadores. Os arquivos MSI podem ser usados com [Microsoft Endpoint Configuration Manager, Política](/configmgr/core/understand/introduction) de [](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)Grupo ou software de distribuição de terceiros, para implantar Teams sua organização. Implantações em massa são úteis porque os usuários não precisam baixar e instalar o cliente Teams manualmente. Em vez disso, Teams será implantado em computadores e, em seguida, iniciar automaticamente na primeira vez que os usuários entrarem em um computador.

Recomendamos que você implante o pacote em computadores em vez de um usuário específico. Ao direcionar computadores, todos os novos usuários desses computadores se beneficiarão dessa implantação.

>[!NOTE]
> Teams também pode ser distribuído para sua organização como parte do Microsoft 365 Apps para Grandes Empresas. Para obter mais informações, confira [Implantar Microsoft Teams com Microsoft 365 Apps para Grandes Empresas](/deployoffice/teams-install).

## <a name="msi-files"></a>Arquivos MSI

A tabela abaixo fornece links para arquivos MSI de 32 bits, 64 bits e ARM64 para Teams. Baixe o MSI que você deseja instalar em computadores em sua organização. A arquitetura x86 (32 bits ou 64 bits) suporta Teams é independente de outros aplicativos Office instalados em um computador.

Se você tiver computadores de 64 bits, recomendamos instalar o MSI de 64 bits Teams mesmo se o computador estiver executando uma versão de 32 bits do Office. O ARM64 MSI só pode ser instalado em computadores que usam a arquitetura ARM, como o Surface Pro X.

> [!IMPORTANT]
> Instale a versão de 64 bits do Teams somente em sistemas operacionais de 64 bits. Se você tentar instalar a versão de 64 bits do Teams em um sistema operacional de 32 bits, a instalação não será bem-sucedida e você não receberá uma mensagem de erro.

|Entidade  |32 bits      |64 bits      | ARM64 |
|---------|---------|---------|-----------|
|Comercial     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Governo dos EUA - GCC     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Governo dos EUA - GCC Alta    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Governo dos EUA - DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Como o Microsoft Teams MSI funciona

### <a name="pc-installation"></a>Instalação no PC

O Teams MSI `%SystemDrive%\Program Files\Teams Installer` coloca um instalador em um Windows de 32 bits `%SystemDrive%\Program Files (x86)\Teams Installer` e em 64 bits Windows. Sempre que um usuário entra em um novo perfil Windows usuário, o instalador é lançado e uma cópia do aplicativo Teams é instalada na pasta desse `%LocalAppData%\Microsoft\Teams` usuário. Se um usuário já tiver o aplicativo Teams `%LocalAppData%\Microsoft\Teams` instalado na pasta, o instalador MSI ignorará o processo para esse usuário.

Os arquivos MSI não podem ser usados para implantar atualizações. O Teams cliente será atualizado automaticamente quando detectar que uma nova versão está disponível no serviço. Para implantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo. Se você implantar uma versão mais antiga do arquivo MSI, o cliente atualizará automaticamente (exceto em ambientes VDI) quando possível para o usuário. Se uma versão muito antiga for implantada, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams.

> [!IMPORTANT]
> Não recomendamos que você altere os locais de instalação padrão, pois isso pode quebrar o fluxo de atualização. Uma versão muito antiga pode impedir que os usuários acessem o serviço.

#### <a name="target-computer-requirements"></a>Requisitos do computador de destino

Certifique-se de que os computadores que você Teams ao atender aos requisitos listados nos [requisitos de hardware para Microsoft Teams](hardware-requirements-for-the-teams-app.md).

### <a name="vdi-installation"></a>Instalação da VDI

Para obter instruções completas sobre como implantar o aplicativo de área de trabalho do Teams na VDI, confira [Teams para Infraestrutura de Área de Trabalho Virtual](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedimento de limpeza e reimplantação

Se um usuário desinstalar o Teams de seu perfil de usuário, o instalador MSI rastreará se o usuário desinstalou o aplicativo do Teams e não instalou mais o Teams para esse perfil de usuário. Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:

> [!IMPORTANT]
> As próximas etapas contêm informações sobre como modificar o registro. Certifique-se de fazer backup do registro antes de modificá-lo e de saber como restaurá-lo se ocorrer um problema. Para obter mais informações sobre como fazer backup, restaurar e modificar o registro, confira [Informações sobre o registro do Windows para usuários avançados](https://support.microsoft.com/help/256986).

1. Desinstale o aplicativo Teams instalado para cada perfil de usuário. Para obter mais informações, confira [Desinstalar o Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Exclua o diretório recursivamente em para `%LocalAppData%\Microsoft\Teams\` cada perfil de usuário.
3. Exclua `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` o valor do Registro para cada perfil de usuário.
4. Reimplantar o arquivo MSI para esse computador específico.

> [!TIP]
> É possível também usar nosso [Script de limpeza de implantação do Teams para concluir as etapas 1 e 2](scripts/powershell-script-deployment-cleanup.md).  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impede que o Teams seja iniciado automaticamente após a instalação

O comportamento padrão do MSI é instalar o aplicativo do Teams assim que um usuário entrar e iniciá-lo automaticamente. Se você não quiser que o Teams inicie automaticamente para os usuários após a instalação, use a Política de Grupo para definir uma configuração de política ou desabilitar o início automático no instalador MSI.

### <a name="use-group-policy-recommended"></a>Usar a Política de Grupo (recomendado)

Habilita **a configuração Impedir Microsoft Teams iniciar automaticamente após a instalação da** [Política de](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) Grupo. Você pode encontrar essa configuração de política **em User** **ConfigurationPoliciesAdministrative**\\\\ **Templates**\\ **Microsoft Teams**. Esse é o método recomendado porque você pode desativar ou ativar a configuração de política de acordo com as necessidades da sua organização.

Ao habilitar esta configuração de política antes de instalar o Teams, o Teams não é iniciado automaticamente quando o usuário entrar no Windows. Após um usuário iniciar o Teams pela primeira vez, o Teams é iniciado automaticamente na próxima vez que o usuário fizer login.

Para saber mais, confira [Use a Política de Grupo para impedir que o Teams seja iniciado automaticamente após a instalação](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Se você já implantou o Teams e deseja definir esta política para desativar o início automático do Teams, defina primeiro a configuração da Política de Grupo com o valor desejado e execute o [script de redefinição do início automático do Teams](scripts/powershell-script-teams-reset-autostart.md) por usuário.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Desabilitar o início automático do instalador MSI

Você pode desabilitar o lançamento automático para o instalador MSI usando o `OPTIONS="noAutoStart=true"` parâmetro da seguinte forma.  

Para a versão de 32 bits:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Para a versão de 64 bits:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Quando um usuário faz logon no Windows, o Teams é instalado com o MSI e um atalho para iniciá-lo é adicionado à área de trabalho do usuário. O Teams não será iniciado até que o usuário inicie-o manualmente. Depois que o usuário iniciar o Teams manualmente, ele iniciará automaticamente sempre que o usuário fizer login.

Observe que esses exemplos também usam o parâmetro **ALLUSERS = 1**. Quando você define este parâmetro, o Instalador de Todo o Computador do Teams aparece em Programas e recursos no Painel de Controle e em Aplicativos e Recursos nas Configurações do Windows para todos os usuários do computador. Todos os usuários podem desinstalar o Teams se tiverem credenciais de administrador no computador.

> [!Note]
> Se executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas. Mesmo que você o execute como administrador, se isso não for feito com permissões elevadas, o instalador não poderá configurar a opção para desabilitar o início automático.
