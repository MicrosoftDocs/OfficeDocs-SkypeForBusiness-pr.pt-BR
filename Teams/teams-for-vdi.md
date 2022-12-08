---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Saiba como executar Microsoft Teams em um ambiente de VDI (Infraestrutura de Área de Trabalho Virtualizada).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a3193b48559fdfc941181963e493d73668bef52
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307746"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para Infraestrutura de Área de Trabalho Virtualizada

Este artigo descreve os requisitos e limitações de usar Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é VDI?

Virtual Desktop Infrastructure (VDI) é a tecnologia de virtualização que hospeda um sistema operacional da área de trabalho e aplicativos em um servidor centralizado em um data center. Isso permite uma experiência de área de trabalho completa e personalizada para usuários com uma fonte centralizada totalmente protegida e compatível.

O Teams em um ambiente virtualizado dá suporte a chat e colaboração. E com as plataformas Azure Virtual Desktop, Citrix e VMware, também há suporte para a funcionalidade de chamada e reunião.

O Teams também dá suporte a várias configurações em ambientes virtuais. Estes incluem modos VDI, dedicados, compartilhados, persistentes e não persistentes. Os recursos estão em desenvolvimento contínuo e são adicionados regularmente, e a funcionalidade se expandirá ao longo do tempo.

Usar o Teams em um ambiente virtualizado pode ser um pouco diferente de usar o Teams em um ambiente não virtualizado. Por exemplo, alguns recursos avançados podem não estar disponíveis em um ambiente virtualizado e a resolução de vídeo pode ser diferente.

Para garantir uma experiência ideal do usuário, siga as diretrizes deste artigo.

> [!Note]
> Para obter detalhes sobre a VDI do Teams em diferentes plataformas, confira [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams em componentes VDI

Usar o Teams em um ambiente virtualizado requer os seguintes componentes.

- **Agente de virtualização: o gerenciador** de recursos e conexões para o provedor de virtualização, como o Azure
- **Área de trabalho virtual**: a pilha de máquina virtual (VM) que executa o Teams
- **Cliente fino**: o dispositivo com o qual o usuário interface fisicamente
- **Aplicativo de área de trabalho do Teams**: o aplicativo cliente da área de trabalho do Teams

## <a name="teams-on-vdi-requirements"></a>Equipes em requisitos de VDI

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O aplicativo de área de trabalho do Teams foi validado com os principais provedores de soluções de virtualização. Com vários provedores de mercado, recomendamos que você consulte seu provedor de soluções de virtualização para garantir que você atenda aos requisitos mínimos.
  
Atualmente, o Teams na VDI com otimização de áudio/vídeo (AV) é certificado com Azure Virtual Desktop, Citrix e VMware. Examine as informações nesta seção para garantir que você atenda a todos os requisitos para a funcionalidade adequada.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para o Teams

As plataformas a seguir têm soluções de infraestrutura de área de trabalho virtual para o Teams.

|Plataforma|Solução|
|----|---|
|![O logotipo que representa Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Área de Trabalho Virtual do Azure</a>, <a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![O logotipo que representa o Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![O logotipo que representa o VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">Horizonte do VMware</a> |

### <a name="azure-virtual-desktop"></a>Área de Trabalho Virtual do Azure

A Área de Trabalho Virtual do Azure fornece otimização de AV para o Teams no VDI. Para saber mais sobre requisitos e instalação, confira [Usar o Teams na Área de Trabalho Virtual do Azure](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 usa a otimização de AV fornecida pela Área de Trabalho Virtual do Azure para garantir experiências ideais do Teams de PCs de nuvem. Para saber mais sobre os requisitos e a instalação, confira [Usar o Teams no Cloud PC](/windows-365/enterprise/teams-on-cloud-pc).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos de Aplicativos Virtuais e Áreas de Trabalho do Citrix

Os Aplicativos Virtuais e Áreas de Trabalho do Citrix (anteriormente conhecidos como XenApp e XenDesktop) fornecem otimização de AV para o Teams no VDI. Com os Aplicativos Virtuais e Áreas de Trabalho do Citrix, o Teams na VDI dá suporte à funcionalidade de chamada e reunião, além de chat e colaboração.

Você pode baixar a versão mais recente de Aplicativos Virtuais e Áreas de Trabalho do Citrix no [site de downloads do Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Você precisará entrar primeiro.) Os componentes necessários são empacotados no [aplicativo Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) e no VDA (Virtual Delivery Agent) por padrão. Você não precisa instalar nenhum componente ou plug-in adicional na CWA ou no VDA.

Para obter os requisitos mais recentes do servidor e do cliente, consulte o artigo [Otimização para Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) no site do Citrix.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos do Workspace e da Área de Trabalho do VMware Horizon

O VMware Horizon é uma plataforma moderna para a entrega segura de áreas de trabalho virtuais e aplicativos em toda a nuvem híbrida. Para oferecer uma ótima experiência ao usuário final, o VMware Horizon fornece otimização de mídia para o Teams. Essa otimização melhora a produtividade geral em áreas de trabalho virtuais e aplicativos e aprimora a experiência do usuário ao chamar e se reunir usando o Teams.

Você pode baixar a versão mais recente do VMware Horizon na página [Downloads do VMware](https://customerconnect.vmware.com/downloads/#all_products) . Os componentes de otimização de mídia necessários fazem parte do Horizon Agent e do Horizon Client por padrão e não há necessidade de instalar nenhum plug-in adicional para usar o recurso de otimização para o Teams.

Para obter os requisitos e instruções mais recentes sobre como configurar a otimização de mídia para o Teams, consulte o artigo [Configurando Otimização de Mídia para Microsoft Teams](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) no site do VMware.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar ou atualizar o aplicativo de área de trabalho do Teams na VDI

Você pode implantar o aplicativo de área de trabalho do Teams para VDI usando uma instalação por computador ou por usuário usando o pacote MSI. Decidir qual abordagem usar depende se você usa uma configuração persistente ou não persistente e as necessidades de funcionalidade associadas de sua organização.

Para uma configuração persistente dedicada, a instalação por computador e por usuário funcionará. No entanto, para uma instalação não persistente, o Teams requer uma instalação por computador para funcionar com eficiência. Consulte a seção [Configuração não persistente](#non-persistent-setup) .

Com a instalação por computador, as atualizações automáticas são desabilitadas. Isso significa que, para atualizar o aplicativo teams, você deve desinstalar a versão atual para atualizar para uma versão mais recente. Com a instalação por usuário, as atualizações automáticas são habilitadas.

> [!IMPORTANT]
> Mantenha o aplicativo de área de trabalho do Teams em seu ambiente de VDI atualizado. Não há suporte para versões do aplicativo de área de trabalho do Teams com datas de lançamento mais de 90 dias mais antigas do que a [data de lançamento da versão atual](/officeupdates/teams-app-versioning) . Versões de aplicativo de área de trabalho do Teams sem suporte mostram uma página de bloqueio para os usuários e solicitam que eles atualizem seu aplicativo.

Para a maioria das implantações de VDI, recomendamos implantar o Teams usando a instalação por computador. Para atualizar para a versão mais recente do Teams, comece com o procedimento de desinstalação seguido pela implantação mais recente da versão do Teams.

Para que a otimização do Teams AV em ambientes de VDI funcione corretamente, o dispositivo de cliente fino deve ter acesso à Internet. Se o acesso à Internet não estiver disponível no dispositivo de cliente fino, a inicialização de otimização não será bem-sucedida. Isso significa que o usuário está em um estado de mídia não otimizado.

#### <a name="dedicated-persistent-setup"></a>Configuração persistente dedicada

Em uma configuração persistente dedicada, as alterações do sistema operacional local dos usuários são mantidas após o logon dos usuários. Para configuração persistente, o Teams dá suporte à instalação por usuário e por computador.

A seguir está a configuração mínima recomendada de VM.

|Parâmetro  |Sistema operacional workstation  |Sistema operacional do servidor  |
|---------|---------|---------|
|Vcpu   |    2 núcleos     |  4, 6 ou 8 núcleos<br>É importante entender a configuração de NUMA (acesso à memória) não uniforme subjacente e configurar suas VMs de acordo.     |
|RAM     |   4 GB      | 512 MB a 1 GB por usuário        |
|Armazenamento    | 8 GB        | 40 GB a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuração não persistente

Em uma configuração não persistente, as alterações do sistema operacional local dos usuários não são retidas após o logon dos usuários. Essas configurações geralmente são sessões compartilhadas com vários usuários. A configuração da VM varia de acordo com o número de usuários e os recursos disponíveis do servidor físico.

Para uma configuração não persistente, o aplicativo de área de trabalho do Teams deve ser instalado por computador na imagem dourada. Isso garante um lançamento eficiente do aplicativo Teams durante uma sessão de usuário. Para saber mais, confira a seção [Instalar ou atualizar o aplicativo de área de trabalho do Teams na VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

Usar o Teams em uma configuração não persistente também requer um gerenciador de cache de perfil para sincronização eficiente de dados de runtime do Teams. A sincronização eficiente de dados garante que as informações específicas do usuário apropriadas (como dados, perfil ou configurações de um usuário) sejam armazenadas em cache durante a sessão do usuário. Verifique se os dados nessas duas pastas estão sincronizados:<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Uma pasta de roaming (ou, se você estiver usando o redirecionamento de pastas, um gerenciador de cache) é necessária para garantir que o aplicativo Teams tenha os dados de runtime e os arquivos necessários para executar o aplicativo. Isso é necessário para atenuar problemas de latência de rede ou falhas de rede, o que de outra forma causaria erros de aplicativo e uma experiência lenta devido a dados e arquivos indisponíveis.

Há uma variedade de soluções do gerenciador de cache disponíveis, como [o FSLogix](/fslogix/overview). Consulte o provedor do gerenciador de cache para obter instruções de configuração específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Lista de exclusão de conteúdo armazenada em cache do Teams para configuração não persistente

Exclua o seguinte da pasta de cache do Teams, `%AppData%/Microsoft/Teams`. Excluir esses itens ajuda a reduzir o tamanho do cache do usuário para otimizar ainda mais sua configuração não persistente.

- .txt arquivos
- Pasta de pilha de mídia
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps para Grandes Empresas considerações

Considere o seguinte quando você implantar o Teams com Microsoft 365 Apps para Grandes Empresas na VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Novas implantações do Teams por meio de Microsoft 365 Apps para Grandes Empresas

Antes de implantar o Teams por meio de Microsoft 365 Apps para Grandes Empresas, primeiro você deve desinstalar todos os aplicativos do Teams pré-existentes se eles foram implantados usando a instalação por computador.

O Teams por meio de Microsoft 365 Apps para Grandes Empresas é instalado por usuário. Para saber mais, confira a seção [Instalar ou atualizar o aplicativo de área de trabalho do Teams na VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Implantações do Teams por meio de atualizações Microsoft 365 Apps para Grandes Empresas

O Teams também está sendo adicionado às instalações existentes de Microsoft 365 Apps para Grandes Empresas. Como Microsoft 365 Apps para Grandes Empresas instala apenas o Teams por usuário, consulte a seção [Instalar ou atualizar o aplicativo de área de trabalho do Teams na VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Usando o Teams com instalação por máquina e Microsoft 365 Apps para Grandes Empresas

Microsoft 365 Apps para Grandes Empresas não dá suporte a instalações por máquina do Teams. Para usar a instalação por computador, você deve excluir o Teams do Microsoft 365 Apps para Grandes Empresas. Consulte a [implantação do aplicativo de área de trabalho do Teams na VM](#deploy-the-teams-desktop-app-to-the-vm) e [Como excluir a implantação do Teams por meio de seções Microsoft 365 Apps para Grandes Empresas](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise).

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Como excluir a implantação do Teams por meio de Microsoft 365 Apps para Grandes Empresas

Para saber mais sobre o Teams e Microsoft 365 Apps para Grandes Empresas, confira [Como excluir o Teams de novas instalações de Microsoft 365 Apps para Grandes Empresas](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) e [Usar Política de Grupo para controlar a instalação do Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implantar o aplicativo de área de trabalho do Teams na VM

⁠1. Baixe o pacote MSI do Teams que corresponde ao sistema operacional VDI VDI usando um dos seguintes links:
    - [Versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)
    > [!NOTE]
    > Para nuvens governamentais, consulte [Instalar em massa o Teams usando o MSI (Windows Installer)](msi-deployment.md) para os links de download para os arquivos MSI.

2. Instale o MSI na VM VDI executando um dos seguintes comandos:

    - Instalação por usuário (padrão)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Esse processo é a instalação padrão, que instala o Teams na pasta de `%AppData%` usuário. Nesse ponto, a configuração da imagem dourada está concluída.

        > [!IMPORTANT]
        > O Teams não funcionará corretamente com a instalação por usuário em uma configuração não persistente.

    - Instalação por computador

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Esse processo adiciona uma chave de registro necessária ao computador que permite que o instalador do Teams saiba que é uma instância de VDI.  Sem ele, o instalador errou, informando: "A instalação falhou.  Não é possível instalar para todos os usuários quando um ambiente VDI não é detectado."

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Esse processo instala o `%ProgramFiles(x86)%` Teams na pasta em um sistema operacional de 64 bits e na `%ProgramFiles%` pasta em um sistema operacional de 32 bits. Nesse ponto, a configuração da imagem dourada está concluída.

        > [!IMPORTANT]
        >  A instalação do Teams por computador é necessária para configurações não persistentes.

        Quando a próxima sessão interativa de logon for iniciada, o Teams inicia e pede credenciais.

        > [!NOTE]
        > Esses exemplos também usam o `ALLUSERS=1` parâmetro. Ao definir esse parâmetro, **o Instalador do Teams Machine-Wide** aparece em **Programas e Recursos** em **Painel de Controle** e em **Aplicativos & recursos** em **Configurações do Windows** para todos os usuários do computador. Todos os usuários poderão desinstalar o Teams se tiverem credenciais de administrador.
        >
        > É importante entender a diferença entre `ALLUSERS=1` e `ALLUSER=1`. O `ALLUSERS=1` parâmetro pode ser usado em ambientes não VDI e VDI, enquanto o `ALLUSER=1` parâmetro é usado apenas em ambientes VDI para especificar uma instalação por máquina.

3. Desinstale o MSI da VM VDI. Há duas maneiras de desinstalar o Teams.

    - **Script do PowerShell**: você pode usar o script do PowerShell de [limpeza de implantação do Teams](scripts/powershell-script-deployment-cleanup.md) para desinstalar o Teams e remover a pasta Teams para um usuário. Execute o script de cada perfil de usuário no qual o Teams foi instalado no computador.
    - **Linha de comando**: execute o seguinte comando.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Esse processo desinstala o `%ProgramFiles(x86)%` Teams da pasta ou `%ProgramFiles%` pasta, dependendo do ambiente do sistema operacional.

## <a name="teams-on-vdi-performance-considerations"></a>Teams em considerações de desempenho de VDI

Há uma variedade de configurações de configuração virtualizadas, cada uma com um foco diferente para otimização. Por exemplo, uma configuração pode se concentrar na densidade do usuário. Ao planejar, considere o seguinte para ajudar a otimizar sua configuração com base nas necessidades de carga de trabalho da sua organização.

- **Requisito mínimo**: algumas cargas de trabalho podem exigir uma instalação usando recursos que estão acima dos requisitos mínimos. Por exemplo, cargas de trabalho para desenvolvedores que usam aplicativos que exigem mais recursos de computação.
- **Dependências: elas** incluem dependências de infraestrutura, carga de trabalho e outras considerações ambientais fora do aplicativo de área de trabalho do Teams.
- **Recursos desabilitados no VDI**: o Teams desabilita recursos intensivos de GPU para VDI, o que pode ajudar a melhorar a utilização transitória da CPU. Os seguintes recursos estão desabilitados:
    - Animação CSS do Teams
    - Início automático do Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Equipes na VDI com chamadas e reuniões

Além de chat e colaboração, o Teams na VDI com chamadas e reuniões está disponível com plataformas de provedor de virtualização com suporte. Os recursos com suporte são baseados na pilha de mídia WebRTC e na implementação do provedor de virtualização. O diagrama a seguir fornece uma visão geral da arquitetura.

![Diagrama mostrando o Teams na arquitetura VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se você atualmente executar o Teams sem otimização de AV no VDI e usar recursos que ainda não têm suporte para otimização (como Dar e assumir o controle quando o compartilhamento de aplicativos), você precisará definir políticas de provedor de virtualização para desativar o redirecionamento do Teams. Isso significa que as sessões de mídia do Teams não serão otimizadas. Para obter etapas sobre como definir políticas para desativar o redirecionamento do Teams, entre em contato com seu provedor de virtualização.

### <a name="network-requirements"></a>Requisitos de rede

Recomendamos que você avalie seu ambiente para identificar quaisquer riscos e requisitos que possam influenciar sua implantação geral de voz na nuvem e vídeo. Use o [Skype for Business Ferramenta de Avaliação de Rede](https://www.microsoft.com/download/details.aspx?id=53885) para testar se sua rede está pronta para o Teams.

Para saber mais sobre como preparar sua rede para o Teams, confira [Preparar a rede da sua organização para o Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar do Skype for Business no VDI para o Teams no VDI

Se você estiver migrando de Skype for Business no VDI para o Teams no VDI, além das diferenças entre os dois aplicativos, haverá algumas diferenças quando o VDI também é implementado. Alguns recursos que atualmente não têm suporte na VDI do Teams que estão no Skype for Business VDI são os seguintes:

- Política por plataforma para desabilitar alguns recursos de AV no VDI
- Dar e assumir o controle quando o compartilhamento de aplicativos
- Compartilhamento de tela do chat sem áudio
- Envio e recebimento simultâneos de vídeo e compartilhamento de tela

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams no navegador Chrome versus aplicativo de área de trabalho do Teams para VDI

O Teams no navegador Chrome não fornece uma substituição para o aplicativo de área de trabalho do Teams para VDI com otimização de AV. A experiência de chat e colaboração funciona conforme o esperado. Quando a mídia é necessária, há algumas experiências que podem não atender às expectativas do usuário no navegador Chrome:

- A experiência de streaming de áudio e vídeo pode não ser ideal. Os usuários podem sofrer atrasos ou qualidade reduzida.
- As configurações do dispositivo não estão disponíveis nas configurações do navegador.
- O gerenciamento de dispositivos é tratado por meio do navegador e requer várias configurações nas configurações do site do navegador.
- As configurações do dispositivo também podem precisar ser definidas no gerenciamento de dispositivos Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams na VDI com chat e colaboração

Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você poderá definir políticas de nível de usuário para desativar a funcionalidade de chamada e reunião no Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e reunião

Você pode definir políticas usando o centro de administração do Teams ou o PowerShell. Até algumas horas para as alterações de política se propagarem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.

[**Chamando polícias**](teams-calling-policy.md): o Teams inclui a política interna de chamada **DisallowCalling** , na qual todos os recursos de chamada são desativados. Atribua a política **DisallowCalling** a todos os usuários da sua organização que usam o Teams em um ambiente virtualizado.

[**Políticas de reunião**](meeting-policies-overview.md): o Teams inclui a política de reunião interna do **AllOff** , na qual todos os recursos de reunião são desativados. Atribua a política **AllOff** a todos os usuários da sua organização que usam o Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Teams

Para atribuir a política de chamada **DisallowCalling** e a política **de reunião AllOff** a um usuário:

1. Na navegação à esquerda do centro de administração do Teams, acesse **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1. Em **Chamar política**, clique **em DisallowCalling**.
    2. Em **Política de reunião**, clique em **AllOff**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na navegação à esquerda do centro de administração do Teams, acesse **Usuários** e pesquise os usuários ou filtre a exibição para mostrar os usuários desejados.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique no **&#x2713;** (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Teams, acesse a política que você deseja atribuir. Por exemplo:
    - Vá para **políticas de Chamada de** **Voz** >  e clique **em DisallowCalling**.
    - Vá para **Políticas de Reunião** de **Reuniões** >  e clique em **AllOff**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar o [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a `DisallowCalling` política de chamada a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar o [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de `AllOff` reunião a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar o Teams no VDI com chat e colaboração para otimizar o Teams com chamadas e reuniões

Se você tiver uma implementação existente do Teams no VDI com chat e colaboração na qual você definiu políticas de nível de usuário para desativar a funcionalidade de chamada e reunião e está migrando para o Teams com otimização de AV, você deve definir políticas para ativar a funcionalidade de chamada e reunião para esses usuários do Teams em VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Definir políticas para ativar a funcionalidade de chamada e reunião

Você pode usar o centro de administração do Teams ou o PowerShell para definir e atribuir políticas de chamada e reunião aos usuários. Pode levar algum tempo (algumas horas) para que as alterações de política sejam propagadas. Se você não vir alterações para uma determinada conta imediatamente, tente novamente após algumas horas.

[**Chamando polícias**](teams-calling-policy.md): as políticas de chamada no Teams controlam quais recursos de chamada estão disponíveis para os usuários. O Teams inclui a política de chamada **AllowCalling** interna, na qual todos os recursos de chamada são ativados. Para ativar todos os recursos de chamada, atribua a política **AllowCalling** . Ou crie uma política de chamada personalizada para ativar os recursos de chamada desejados e atribuí-la aos usuários.

[**Políticas de**](meeting-policies-overview.md) reunião: as políticas de reunião no Teams controlam os tipos de reuniões que os usuários podem criar e os recursos disponíveis para os participantes da reunião agendados pelos usuários em sua organização. O Teams inclui a política de reunião **allon** interna, na qual todos os recursos de reunião estão ativados. Para ativar todos os recursos de reunião, atribua a política **AllOn** . Ou crie uma política de reunião personalizada para ativar os recursos de reunião desejados e atribuí-los aos usuários.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Teams

Para atribuir a política **de chamada AllowCalling** e a política **de reunião AllOn** a um usuário:

1. Na navegação à esquerda do centro de administração do Teams, acesse **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1. Em **Chamar política**, clique em **PermitirChamar**.
    2. Em **Política de reunião**, clique em **AllOn**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na navegação à esquerda do centro de administração do Teams, acesse **Usuários** e pesquise os usuários ou filtre a exibição para mostrar os usuários desejados.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique no **&#x2713;** (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Teams, acesse a política que você deseja atribuir. Por exemplo:
    - Vá para **políticas de Chamada de** **Voz** >  e clique em **PermitirChing**.
    - Acesse **Políticas** de **reunião de reuniões** >  e clique em **AllOn**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar o [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a `AllowCalling` política de chamada a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar o [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de `AllOn` reunião a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Modo de fallback de controle no Teams

Quando os usuários se conectam de um ponto de extremidade sem suporte, os usuários estão no modo fallback, no qual o AV não é otimizado. Você pode desabilitar ou habilitar o modo de fallback definindo um dos seguintes valores de registro `DWORD` :

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

Para desabilitar o modo de fallback, defina o valor como **1**. Para habilitar somente áudio, defina o valor como **2**. Se o valor não estiver presente ou estiver definido como **0** (zero), o modo de fallback estará habilitado.

Esse recurso está disponível no Teams versão 1.3.00.13565 e posterior.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Desabilitar configurações de áudio e vídeo para VDI

As políticas de VDI do Teams estão disponíveis no módulo do Teams. Essas políticas são ativas e impostas em ambientes VDI não otimizados.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> Isso é apenas para ambientes não otimizados.

### <a name="connect-to-microsoft-teams-powershell"></a>Conectar-se ao Microsoft Teams PowerShell

Siga as instruções em [Instalar Microsoft Módulo do Teams PowerShell](/Teams/teams-powershell-install.md) para se conectar ao módulo Microsoft Teams PowerShell. Em seguida, execute o seguinte comando para confirmar se todos os cmdlets VDI estão disponíveis:

```PowerShell
Get-Command -Noun *VDI*
```

### <a name="set-policies-to-limit-calling-features"></a>Definir políticas para limitar recursos de chamada

Quando os usuários cuja política de VDI `DisableCallsAndMeetings` está definida para `$true` entrar no Teams no VDI, eles não podem:

- Faça chamadas.
- Ingressar em reuniões.
- Compartilhamento de tela do chat.

Todos os tipos de chamada devem ser desabilitados.

> [!NOTE]
> Isso é apenas para ambientes não otimizados.

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

Quando os usuários cuja política de VDI `DisableAudioVideoInCallsAndMeetings` está definida para `$true` entrar no Teams no VDI, eles:

- Pode exibir o compartilhamento do chat.
- Pode participar de uma reunião e compartilhar uma tela e mover seu áudio para um telefone.
- Não é possível manter chamadas de áudio e vídeo de pessoa para pessoa da VDI.

> [!NOTE]
> Isso é apenas para ambientes não otimizados.

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>Problemas e limitações conhecidos

### <a name="client-deployment-installation-and-setup"></a>Implantação, instalação e instalação do cliente

- Com a instalação por computador, o Teams no VDI não é atualizado automaticamente da maneira que os clientes não VDI Teams são. Você precisa atualizar a imagem da VM instalando um novo MSI conforme descrito na seção [Instalar ou atualizar o aplicativo de área de trabalho do Teams na seção VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- Em ambientes Citrix, se o usuário se desconectar da Máquina Virtual enquanto o Teams estiver em execução, as atualizações do Teams poderão fazer com que o usuário esteja em um estado não otimizado para AV quando se reconectar. Recomendamos que os usuários abandonem o Teams antes de se desconectarem da Máquina Virtual Citrix para evitar esse cenário.
- As equipes devem ser implantadas por usuário ou por computador. Não há suporte para a implantação do Teams para simultaneidade por usuário e por computador. Para migrar de por computador ou por usuário para um desses modos, siga o procedimento de desinstalação e reimplante para qualquer modo.
- A Área de Trabalho Virtual do Azure não dá suporte a clientes baseados em Linux no momento.
- A opção de locatário rápido pode resultar em problemas relacionados à chamada no VDI, como o compartilhamento de tela não disponível. Reiniciar o cliente reduzirá esses problemas.

### <a name="notifications"></a>Notificações

- Não há suporte para notificação e presença da contagem de mensagens na barra de tarefas do Windows em um host Windows Server 2016.

### <a name="calling-and-meetings"></a>Chamadas e reuniões

Não há suporte para os seguintes recursos de chamada e reunião:

- Botões HID e controles LED entre o aplicativo Teams e dispositivos para Citrix e VMware
- Desfoque e efeitos em segundo plano para Citrix e VMware
- Funções de produtor e apresentador de eventos ao vivo e transmissão
- Location-Based Roteamento (LBR)
- Tom de retorno de chamada PSTN
- Som de áudio/computador do sistema compartilhado
- Bypass de mídia para Roteamento Direto
- Controle zoom

> [!NOTE]
> Estamos trabalhando na adição de recursos de chamada e reunião que atualmente estão disponíveis apenas em ambientes não VDI. Isso pode incluir mais controle de administrador sobre qualidade, cenários adicionais de compartilhamento de tela e recursos avançados adicionados recentemente ao Teams. Entre em contato com o representante do Teams para saber mais sobre os próximos recursos.

Veja a seguir problemas e limitações conhecidos para chamadas e reuniões:

- A interoperabilidade com Skype for Business é limitada a chamadas de áudio; não há modalidade de vídeo.
- A resolução de fluxo de vídeo de entrada e saída é limitada à resolução de 720p.
- O Teams não alterna para usar o último dispositivo de áudio selecionado pelo usuário, se o dispositivo estiver desconectado e reconectado.
- Eventos ao vivo não são otimizados.
- Compartilhamento de tela de saída:
  - Não há suporte para compartilhamento de aplicativos para VMware e AVD/W365.
- Dê controle e assuma o controle:
  - Não há suporte durante a sessão de compartilhamento de aplicativos.

Para problemas conhecidos do Teams que não estão relacionados à VDI, consulte [Equipes de Suporte em sua organização](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Solução de problemas

### <a name="troubleshoot-citrix-components"></a>Solucionar problemas de componentes do Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Falhas do Teams ou a tela de entrada do Teams está em branco

Esse é um problema conhecido com as versões do VDA do Citrix 1906 e 1909. Para contornar esse problema, adicione o valor do registro `DWORD` a seguir e defina-o como `204` (hexadecimal).

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

Em seguida, reinicie o VDA. Para saber mais, confira este artigo de suporte do Citrix, [solução de problemas de otimização HDX para Microsoft Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar em massa o Teams usando o MSI (Instalador do Windows)](msi-deployment.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar Microsoft Teams na Área de Trabalho Virtual do Azure](/azure/virtual-desktop/teams-on-wvd)
