---
title: Instalar o Microsoft Teams usando MSI via SCCM
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Os administradores podem usar o Teams MSI para implantar em massa o Microsoft Teams para usuários ou computadores selecionados.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8412b6998e824c05ac4d7f394d2283c265f78b04
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "31749681"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar o Microsoft Teams usando MSI
=================================

> [!Tip]
> Assista a sessão a seguir para saber mais sobre os benefícios do cliente de Desktop do Windows, como planejar para ele e como implantá-lo: [Equipes Windows Desktop Client](https://aka.ms/teams-clients)

Para usar o System Center Configuration Manager ou política de grupo ou qualquer mecanismos de distribuição de terceiros para implantação em larga escala, a Microsoft forneceu arquivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa de equipes para selecionar os usuários ou computadores. Os administradores podem usar esses arquivos para implantar remotamente equipes para que os usuários não precisam baixar manualmente o aplicativo de equipes. Quando implantado, equipes gerará automaticamente lançamento para todos os usuários que entram nesta máquina. (É possível desabilitar depois de instalar o aplicativo de início automático. [Veja abaixo](#disable-auto-launch-for-the-msi-installer).) Recomendamos que você implante o pacote para o computador, para que todos os novos usuários do computador também serão beneficiados com essa implantação. 
 
> [!Note] 
> Para saber mais sobre SCCM, consulte [Introdução para o System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimento de implantação (recomendado)
1. Recupere o pacote mais recente.
2. Use os padrões pré-preenchido pelo MSI.
3. Implante em computadores quando possível.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Como funciona ao pacote MSI de equipes da Microsoft

### <a name="pc-installation"></a>Instalação de PC

> [!Note] 
> Consulte [a instalação de VDI](#vdi-installation) para obter orientação sobre como implantar as equipes em um ambiente Virtual DesktopInfrastructure (VDI).

O MSI equipes colocará um instalador em arquivos de programa. Sempre que um usuário se conecta em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo equipes será instalada na pasta de appdata desse usuário. Se um usuário já tiver o aplicativo de equipes instalado na pasta appdata, o instalador MSI irá ignorar o processo para esse usuário.

Não use o MSI para implantar atualizações, pois o cliente irá atualizar automaticamente quando detecta que uma nova versão é disponibilizada pelo serviço. Para reimplantar o instalador mais recente use o processo de reimplantando MSI descrito abaixo.Se você implantar uma versão mais antiga do pacote do MSI, o cliente será atualizado automaticamente sempre que possível para o usuário. Se uma versão antiga muito obtém implantada, o MSI irá disparar uma atualização do aplicativo antes que o usuário seja capaz de usar equipes. 

> [!Important] 
> Não recomendamos que você altere os locais de instalação padrão, como isso poderia quebrará o fluxo de atualização. Ter uma versão antiga muito eventualmente bloqueará os usuários acessem o serviço. 

#### <a name="target-computer-requirements"></a>Requisitos do computador de destino

- .NET framework 4.5 ou posterior
- Windows 7 ou posterior
- 3 GB de espaço em disco para cada perfil de usuário (recomendado)

### <a name="vdi-installation"></a>Instalação de VDI

Aqui é o processo para implantar o aplicativo de área de trabalho de equipes. Para obter orientação completa, consulte [as equipes de infraestrutura de área de trabalho virtualizados](teams-for-vdi.md).

1. Baixe o pacote MSI equipes usando um dos links a seguir, dependendo do ambiente. Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.

    - [versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Execute o seguinte comando para instalar o MSI do VM VDI (ou concluir atualizá-lo).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Essa etapa instala equipes para arquivos de programa. Neste ponto, a configuração de imagem de ouro estará concluída.

    A próxima sessão de logon interativo inicia equipes e solicita credenciais. Observe que não é possível desabilitar a inicialização automática das equipes ao instalar equipes em VDI usando a propriedade ALLUSER.

3. Execute o seguinte comando para desinstalar o MSI de VDI VM (ou se preparar para atualizá-lo).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Isso desinstala equipes de arquivos de programa.

## <a name="clean-up-and-redeployment-procedure"></a>Limpeza e o procedimento de reimplantação

Se um usuário desinstala equipes de seu perfil de usuário, o instalador MSI irá controlar que o usuário tiver desinstalado o aplicativo de equipes e não são mais instalar equipes para esse perfil de usuário. Para reimplantar equipes para esse usuário em um computador particular, onde ele foi desinstalado, faça o seguinte:

1. Desinstale o aplicativo de equipes instalado para cada perfil de usuário. 
2. Após a desinstalação, exclua o diretório recursivamente em % localappdata%\Microsoft\Teams\.
3. Reimplante o pacote MSI nesse computador específico.

> [!TIP] 
> Você pode usar o nosso script de [implantação de equipes da Microsoft limpar](scripts/Powershell-script-teams-deployment-clean-up.md) para realizar as etapas 1 e 2 por meio do SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Desabilitar o recurso de início automático para o instalador MSI

Comportamento padrão do MSI é instalar o cliente de equipes, assim que um usuário entrar e iniciar automaticamente o equipes. Você pode modificar esse comportamento com os parâmetros abaixo da seguinte maneira:

- Quando um usuário fizer logon no Windows, equipes serão instaladas com o MSI
- No entanto, o cliente de equipes não será iniciado até que o usuário tiver iniciado equipes manualmente
- Um atalho para iniciar as equipes será adicionado na área de trabalho do usuário
- Uma vez iniciado manualmente, equipes serão inicialização automática sempre que o usuário fizer logon

Para obter a versão de 32 bits
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Para obter a versão de 64 bits
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Se você executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas. Mesmo se você executá-lo como um administrador, sem executá-lo com permissões elevadas, o instalador não poderão configurar a opção para desabilitar AutoIniciar.
