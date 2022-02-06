---
title: Instalar o Microsoft Teams usando o Microsoft Endpoint Configuration Manager
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Use o Microsoft Endpoint Configuration Manager para implantar em massa o Microsoft Teams para selecionar usuários ou computadores.
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
---

# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Instalar o Microsoft Teams usando o Microsoft Endpoint Configuration Manager

> [!Tip]
> Assista à sessão a seguir para aprender sobre os benefícios do Cliente de Área de trabalho Windows, como planejá-lo e como implantá-lo[: o Teams do Cliente de área de trabalho Windows](https://aka.ms/teams-clients).

Para usar o Microsoft Endpoint Configuration Manager, a Política de Grupo ou qualquer mecanismo de distribuição de terceiros para ampla implantação, a Microsoft oferece arquivos MSI (de 32 bits e 64 bits) que os administradores podem usar para a implantação em massa do Teams para usuários ou computadores selecionados. Os administradores podem usar esses arquivos para implantar o Teams remotamente, de modo que os usuários não precisem baixar manualmente o aplicativo Teams. Quando implantado, o Teams iniciará automaticamente para todos os usuários que fizerem logon naquele computador. (Você pode desabilitar o início automático depois de instalar o aplicativo. [Confira abaixo](#disable-auto-launch-for-the-msi-installer).) É recomendável implantar o pacote no computador para que todos os novos usuários dele também se beneficiem com a implantação.

Estes são os links para os arquivos MSI:

|Entidade  |32 bits      |64 bits      | ARM64 |
|---------|---------|---------|-----------|
|Comercial     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Governo dos EUA - GCC     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Governo dos EUA - GCC Alta    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Governo dos EUA - DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

**Para garantir uma implantação bem-sucedida, esteja ciente do seguinte:**

- Instale a versão de 64 bits do Teams em sistemas operacionais de 64 bits. Se você tentar instalar a versão de 64 bits do Teams em um sistema operacional de 32 bits, a instalação não terá êxito e você não receberá uma mensagem de erro.

- O Teams também podem ser incluído com uma implantação do Microsoft 365 Apps para Grandes Empresas. Para obter mais informações, confira [Implantar Microsoft Teams com Microsoft 365 Apps para Grandes Empresas](/deployoffice/teams-install).

- Para saber mais sobre o Microsoft Endpoint Configuration Manager, confira [O que é o Configuration Manager?](/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>Procedimento de implantação (recomendado)

1. Recupere o pacote mais recente.
2. Use os padrões pré-preenchidos pelo MSI.
3. Implante nos computadores quando possível.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como o pacote Microsoft Teams MSI funciona

### <a name="pc-installation"></a>Instalação no PC

O Teams MSI colocará um instalador em Arquivos de Programas. Sempre que um usuário fizer logon em um novo perfil de usuário do Windows, o instalador será iniciado, e uma cópia do aplicativo Teams será instalada na pasta `AppData` desse usuário. Se o usuário já tiver o aplicativo Teams instalado na pasta `AppData`, o instalador do MSI ignorará o processo para esse usuário.

Não use o MSI para implantar atualizações, pois o cliente atualizará automaticamente quando detectar que há uma nova versão disponível no serviço. Para reimplantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo. Se você implantar uma versão mais antiga do pacote MSI, o cliente atualizará automaticamente (exceto em ambientes da VDI) para o usuário quando possível. Se uma versão muito antiga for implantada, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams.

> [!IMPORTANT]
> O local padrão é C:\Program Files\Teams Installer em sistemas operacionais de 32 bits e C:\Arquivos de Programas (x86)\Teams Instalador em sistemas operacionais de 64 bits.
> Não recomendamos mudar os locais de instalação padrão, pois isso pode interromper o fluxo de atualização. Uma versão muito antiga pode impedir que os usuários acessem o serviço.

#### <a name="target-computer-requirements"></a>Requisitos do computador de destino

- .NET framework 4.5 ou posterior
- Windows 8.1 ou posterior
- Windows Server 2012 R2 ou posterior
- 3 GB de espaço em disco para cada perfil de usuário (recomendado)

### <a name="vdi-installation"></a>Instalação da VDI

Para obter instruções completas sobre como implantar o aplicativo de área de trabalho do Teams na VDI, confira [Teams para Infraestrutura de Área de Trabalho Virtual](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedimento de limpeza e reimplantação

Se um usuário desinstalar o Teams de seu perfil de usuário, o instalador MSI rastreará se o usuário desinstalou o aplicativo do Teams e não instalou mais o Teams para esse perfil de usuário. Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:

> [!IMPORTANT]
> As próximas etapas contêm informações sobre como modificar o registro. Certifique-se de fazer backup do registro antes de modificá-lo e de saber como restaurá-lo se ocorrer um problema. Para obter mais informações sobre como fazer backup, restaurar e modificar o registro, confira [Informações sobre o registro do Windows para usuários avançados](https://support.microsoft.com/help/256986).

1. Desinstale o aplicativo Teams instalado para cada perfil de usuário. Para obter mais informações, confira [Desinstalar o Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Exclua o diretório recursivamente em `%localappdata%\Microsoft\Teams\`.
3. Exclua o valor de registro `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi`.
4. Reimplante o pacote MSI no computador específico.

> [!TIP]
> É possível também usar nosso [Script de limpeza de implantação do Teams para concluir as etapas 1 e 2](scripts/powershell-script-deployment-cleanup.md).  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impede que o Teams seja iniciado automaticamente após a instalação

O comportamento padrão do MSI é instalar o aplicativo do Teams assim que um usuário entrar e iniciá-lo automaticamente. Se você não quiser que o Teams inicie automaticamente para os usuários após a instalação, use a Política de Grupo para definir uma configuração de política ou desabilitar o início automático no instalador MSI.

### <a name="use-group-policy-recommended"></a>Usar a Política de Grupo (recomendado)

Habilite a configuração de Política de Grupo **Impedir que o Microsoft Teams seja iniciado automaticamente após a instalação**. É possível encontrar essa configuração de política em Configuração do Usuário\Políticas\Modelos Administrativos\Microsoft Teams. Esse é o método recomendado porque você pode desativar ou ativar a configuração de política de acordo com as necessidades da sua organização.

Ao habilitar esta configuração de política antes de instalar o Teams, o Teams não é iniciado automaticamente quando o usuário entrar no Windows. Após um usuário iniciar o Teams pela primeira vez, o Teams é iniciado automaticamente na próxima vez que o usuário fizer login.

Para saber mais, confira [Use a Política de Grupo para impedir que o Teams seja iniciado automaticamente após a instalação](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Se você já implantou o Teams e deseja definir esta política para desativar o início automático do Teams, defina primeiro a configuração da Política de Grupo com o valor desejado e execute o [script de redefinição do início automático do Teams](scripts/powershell-script-teams-reset-autostart.md) por usuário.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Desabilitar o início automático do instalador MSI

Você pode desabilitar o início automático do instalador MSI usando o parâmetro **OPTIONS="noAutoStart=true"** da seguinte maneira.  

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
