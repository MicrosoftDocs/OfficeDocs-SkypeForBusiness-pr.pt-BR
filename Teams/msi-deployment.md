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
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238662"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar o Microsoft Teams usando MSI
=================================

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios do cliente da área de trabalho do Windows, como planejar e como implantá-lo: [cliente de área de trabalho do Microsoft Teams](https://aka.ms/teams-clients)

Para usar o System Center Configuration Manager ou a política de grupo ou qualquer mecanismo de distribuição de terceiros para implantação ampla, a Microsoft forneceu arquivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) e [64](https://aka.ms/teams64bitmsi)bits) que os administradores podem usar para a implantação em massa de Teams para selecionar usuários ou computadores. Os administradores podem usar esses arquivos para implantar equipes remotamente para que os usuários não precisem baixar manualmente o aplicativo Teams. Quando implantada, o Microsoft Teams será iniciado automaticamente para todos os usuários que entrarem nesse computador. (Você pode desabilitar o início automático após a instalação do aplicativo. [Veja abaixo](#disable-auto-launch-for-the-msi-installer).) Recomendamos que você implante o pacote no computador para que todos os novos usuários do computador também se beneficiem dessa implantação. 

As equipes também podem ser incluídas com uma implantação do Office 365 ProPlus. Para obter mais informações, consulte [implantar o Microsoft Teams com o Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).
 
> [!Note] 
> Para saber mais sobre o SCCM, confira [introdução ao System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimento de implantação (recomendado)
1. Recupere o pacote mais recente.
2. Use os padrões previamente preenchidos pelo MSI.
3. Implantar para computadores quando possível.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como funciona o pacote MSI do Microsoft Teams

### <a name="pc-installation"></a>Instalação do PC

> [!Note] 
> Confira a [instalação do VDI](#vdi-installation) para obter orientação sobre como implantar o Microsoft Teams em um ambiente virtual DESKTOPINFRASTRUCTURE (VDI).

O MSI do teams colocará um instalador em arquivos de programas. Sempre que um usuário entrar em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo Teams será instalada na pasta AppData daquele usuário. Se um usuário já tiver o aplicativo Teams instalado na pasta AppData, o instalador do MSI ignorará o processo desse usuário.

Não use o MSI para implantar atualizações, porque o cliente será atualizado automaticamente quando detectar que uma nova versão está disponível no serviço. Para implantar novamente o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.Se você implantar uma versão mais antiga do pacote MSI, o cliente será atualizado automaticamente (exceto em ambientes VDI) quando possível para o usuário. Se uma versão muito antiga for implantada, o MSI disparará uma atualização de aplicativo antes que o usuário possa usar o Microsoft Teams. 

> [!Important] 
> Não recomendamos que você altere os locais de instalação padrão, pois isso pode interromper o fluxo de atualização. Com uma versão muito antiga, você poderá impedir que os usuários acessem o serviço. 

#### <a name="target-computer-requirements"></a>Requisitos do computador de destino

- .NET Framework 4,5 ou posterior
- Windows 7 ou posterior
- 3 GB de espaço em disco para cada perfil de usuário (recomendado)

### <a name="vdi-installation"></a>Instalação do VDI

Aqui está o processo para implantar o aplicativo da área de trabalho Teams. Para obter uma orientação completa, consulte [Teams for Virtual Desktop Infrastructure](teams-for-vdi.md).

1. Baixe o pacote MSI do teams usando um dos links a seguir, dependendo do ambiente. Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.

    - [versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Execute o seguinte comando para instalar o MSI na VM VDI (ou conclua a atualização).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Isso instala o Microsoft Teams para arquivos de programas. Neste ponto, a configuração da imagem dourada está completa.

    A próxima sessão de logon interativo inicia o Teams e solicita credenciais. Observe que não é possível desabilitar a inicialização automática de equipes ao instalar o Microsoft Teams no VDI usando a propriedade MyUser.

3. Execute o comando a seguir para desinstalar o MSI da VM VDI (ou preparar-se para atualizá-lo).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Isso desinstala equipes de arquivos de programas.

## <a name="clean-up-and-redeployment-procedure"></a>Procedimento de limpeza e reimplantação

Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI acompanhará que o usuário desinstalou o aplicativo Teams e não instalará mais equipes para esse perfil de usuário. Para reimplantar equipes para este usuário em um determinado computador onde ela foi desinstalada, faça o seguinte:

1. Desinstalar o aplicativo Teams instalado para cada perfil de usuário. 
2. Após a desinstalação, excluir o diretório recursivamente em%localappdata%\Microsoft\Teams\.
3. Reimplante o pacote MSI nesse computador específico.

> [!TIP] 
> Você pode usar o script de [limpeza de implantação do Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para executar as etapas 1 e 2 via SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Desabilitar o início automático para o instalador MSI

O comportamento padrão do MSI é instalar o cliente do teams assim que um usuário entrar e iniciar automaticamente o Microsoft Teams. Você pode modificar esse comportamento com os parâmetros abaixo da seguinte maneira:

- Quando um usuário faz logon no Windows, o Microsoft Teams será instalado com o MSI
- No entanto, o cliente do Teams não iniciará até que o usuário inicie manualmente as equipes
- Um atalho para iniciar equipes será adicionado à área de trabalho do usuário
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
>  Se você executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas. Mesmo que você o execute como administrador, sem executá-lo com permissões elevadas, o instalador não poderá configurar a opção de desabilitar o início automático.
