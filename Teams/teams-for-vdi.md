---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Saiba como executar o Microsoft Teams em um ambiente VDI (Virtualized Desktop Infrastructure).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce8e702682ebcc4b05e94f077882d51f09aac0ff
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624145"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para Infraestrutura de Área de Trabalho Virtualizada

Este artigo descreve os requisitos e as limitações do uso Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é a VDI?

Virtual Desktop Infrastructure (VDI) é uma tecnologia de virtualização que hospeda um sistema operacional da área de trabalho e aplicativos em um servidor centralizado em um data center. Isso permite uma experiência de área de trabalho completa e personalizada para usuários com uma fonte centralizada totalmente segura e compatível.

Teams em um ambiente virtualizado dá suporte a chat e colaboração. E com as plataformas de Área de Trabalho Virtual do Azure, Citrix e VMware, também há suporte para a funcionalidade de chamada e reunião.

Teams também dá suporte a várias configurações em ambientes virtuais. Isso inclui modos VDI, dedicados, compartilhados, persistentes e não persistentes. Os recursos estão em desenvolvimento contínuo e são adicionados regularmente, e a funcionalidade se expandirá ao longo do tempo.

Usar Teams em um ambiente virtualizado pode ser um pouco diferente de usar Teams em um ambiente não virtualizado. Por exemplo, alguns recursos avançados podem não estar disponíveis em um ambiente virtualizado e a resolução de vídeo pode ser diferente.

Para garantir uma experiência de usuário ideal, siga as diretrizes neste artigo.

> [!Note]
> Para obter detalhes sobre Teams VDI em diferentes plataformas, [consulte Teams recursos por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams em componentes VDI

Usar Teams em um ambiente virtualizado requer os seguintes componentes.

- **Agente de virtualização**: o gerenciador de recursos e conexões para o provedor de virtualização, como o Azure
- **Área de** trabalho virtual: a pilha de VM (máquina virtual) que executa Teams
- **Cliente fino**: o dispositivo com o qual o usuário se interface fisicamente
- **Teams da área de** trabalho: o Teams cliente da área de trabalho

## <a name="teams-on-vdi-requirements"></a>Teams requisitos de VDI

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O Teams da área de trabalho foi validado com os principais provedores de solução de virtualização. Com vários provedores de mercado, recomendamos que você consulte seu provedor de soluções de virtualização para garantir que atenda aos requisitos mínimos.
  
Atualmente, o Teams VDI com otimização de áudio/vídeo (AV) é certificado com a Área de Trabalho Virtual do Azure, Citrix e VMware. Examine as informações nesta seção para garantir que você atenda a todos os requisitos para a funcionalidade adequada.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para Teams

As plataformas a seguir têm soluções de infraestrutura de área de trabalho virtual para Teams.

|Plataforma|Solução|
|----|---|
|![O logotipo que representa a Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Área de Trabalho Virtual do Azure</a><a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">, Windows 365</a> |
|![O logotipo que representa a Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![O logotipo que representa o VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Área de Trabalho Virtual do Azure

A Área de Trabalho Virtual do Azure fornece otimização av para Teams na VDI. Para saber mais sobre requisitos e instalação, [consulte Usar Teams área de trabalho virtual do Azure](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 usa a otimização av fornecida pela Área de Trabalho Virtual do Azure para garantir experiências Teams de computadores na nuvem. Para saber mais sobre requisitos e instalação, [consulte Usar Teams pc na nuvem](/windows-365/enterprise/teams-on-cloud-pc).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos do Citrix Virtual Apps and Desktops

Os Aplicativos Virtuais e Áreas de Trabalho do Citrix (anteriormente conhecidos como XenApp e XenDesktop) fornecem otimização av para Teams na VDI. Com os Aplicativos Virtuais e Áreas de Trabalho do Citrix, o Teams na VDI dá suporte à funcionalidade de chamada e reunião, além de chat e colaboração.

Você pode baixar a versão mais recente dos Aplicativos Virtuais e Áreas de Trabalho do Citrix no [site de downloads do Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Você precisará entrar primeiro.) Os componentes necessários são agrupados no [aplicativo Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) e no VDA (Virtual Delivery Agent) por padrão. Você não precisa instalar nenhum componente ou plug-in adicional no CWA ou no VDA.

Para obter os requisitos mais recentes do servidor e do cliente, consulte [o artigo De](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) otimização Microsoft Teams no site da Citrix.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos do Workspace e da Área de Trabalho do VMware Horizon

O VMware Horizon é uma plataforma moderna para entrega segura de áreas de trabalho virtuais e aplicativos em toda a nuvem híbrida. Para oferecer uma ótima experiência ao usuário final, o VMware Horizon fornece otimização de mídia para Teams. Essa otimização melhora a produtividade geral em áreas de trabalho virtuais e aplicativos e melhora a experiência do usuário ao chamar e reunião usando Teams.

Você pode baixar a versão mais recente do VMware Horizon na página [Downloads do VMware](https://customerconnect.vmware.com/downloads/#all_products) . Os componentes de otimização de mídia necessários fazem parte do Agente do Horizon e do Cliente horizon por padrão e não há necessidade de instalar nenhum plug-in adicional para usar o recurso de otimização para Teams.

Para obter os requisitos [e](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) instruções mais recentes sobre como configurar a otimização de mídia para Teams, consulte o artigo Configurando a Otimização de Mídia para Microsoft Teams no site do VMware.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar ou atualizar o Teams da área de trabalho no VDI

Você pode implantar o Teams da área de trabalho para VDI usando uma instalação por computador ou por usuário usando o pacote MSI. Decidir qual abordagem usar depende se você usa uma configuração persistente ou não persistente e as necessidades de funcionalidade associadas de sua organização.

Para uma configuração persistente dedicada, a instalação por computador e por usuário funcionará. No entanto, para uma configuração não persistente, o Teams requer uma instalação por computador para funcionar com eficiência. Consulte a [seção de configuração não](#non-persistent-setup) persistente.

Com a instalação por computador, as atualizações automáticas são desabilitadas. Isso significa que, para atualizar o Teams, você deve desinstalar a versão atual para atualizar para uma versão mais recente. Com a instalação por usuário, as atualizações automáticas são habilitadas.

Para a maioria das implantações de VDI, recomendamos que você implante Teams usando a instalação por computador. Para atualizar para a versão mais Teams, comece com o procedimento de desinstalação seguido pela implantação Teams versão mais recente.

Para Teams otimização av em ambientes VDI funcione corretamente, o dispositivo cliente fino deve ter acesso à Internet. Se o acesso à Internet não estiver disponível no dispositivo de cliente fino, a inicialização de otimização não será bem-sucedida. Isso significa que o usuário está em um estado de mídia não otimizado.

#### <a name="dedicated-persistent-setup"></a>Configuração persistente dedicada

Em uma configuração persistente dedicada, as alterações do sistema operacional local dos usuários são mantidas após o logoff dos usuários. Para configuração persistente, Teams dá suporte à instalação por usuário e por computador.

A seguir está a configuração mínima de VM recomendada.

|Parâmetro  |Sistema operacional de estação de trabalho  |Sistema operacional do servidor  |
|---------|---------|---------|
|Vcpu   |    2 núcleos     |  4, 6 ou 8 núcleos<br>É importante entender a configuração subjacente de NUMA (acesso à memória não uniforme) e configurar suas VMs adequadamente.     |
|RAM     |   4 GB      | 512 MB a 1 GB por usuário        |
|Armazenamento    | 8 GB        | 40 GB a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuração não persistente

Em uma configuração não persistente, as alterações do sistema operacional local dos usuários não são mantidas após o logoff dos usuários. Essas configurações são normalmente sessões de vários usuários compartilhadas. A configuração da VM varia de acordo com o número de usuários e os recursos de servidor físico disponíveis.

Para uma configuração não persistente, o Teams da área de trabalho deve ser instalado por computador na imagem dourada. Isso garante uma inicialização eficiente do aplicativo Teams durante uma sessão do usuário. Para saber mais, confira a [seção Instalar ou atualizar o Teams da área de trabalho na VDI](#install-or-update-the-teams-desktop-app-on-vdi).

Usar Teams em uma configuração não persistente também requer um gerenciador de cache de perfil para uma sincronização de dados Teams runtime eficiente. A sincronização eficiente de dados garante que as informações específicas do usuário apropriadas (como dados, perfil ou configurações do usuário) são armazenadas em cache durante a sessão do usuário. Verifique se os dados nessas duas pastas estão sincronizados:<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Uma pasta móvel (ou, se você estiver usando o redirecionamento de pasta, um gerenciador de cache) é necessária para garantir que o aplicativo Teams tenha os dados e os arquivos de runtime necessários para executar o aplicativo. Isso é necessário para atenuar problemas de latência de rede ou falhas de rede, o que poderia causar erros de aplicativo e uma experiência lenta devido a dados e arquivos indisponíveis.

Há uma variedade de soluções de gerenciador de cache disponíveis, como [FSLogix](/fslogix/overview). Consulte o provedor do gerenciador de cache para obter instruções de configuração específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams lista de exclusão de conteúdo armazenado em cache para configuração não persistente

Exclua o seguinte da pasta Teams cache, `%AppData%/Microsoft/Teams`. Excluir esses itens ajuda a reduzir o tamanho do cache do usuário para otimizar ainda mais sua configuração não persistente.

- .txt arquivos
- Pasta de pilha de mídia
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps para Grandes Empresas considerações

Considere o seguinte ao implantar Teams com Microsoft 365 Apps para Grandes Empresas na VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Novas implantações de Teams por meio Microsoft 365 Apps para Grandes Empresas

Antes de implantar Teams por meio do Microsoft 365 Apps para Grandes Empresas, você deve primeiro desinstalar todos os aplicativos Teams existentes se eles foram implantados usando a instalação por computador.

Teams por Microsoft 365 Apps para Grandes Empresas é instalado por usuário. Para saber mais, confira a [seção Instalar ou atualizar o Teams da área de trabalho na VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams implantações por meio Microsoft 365 Apps para Grandes Empresas atualizações

Teams também está sendo adicionado às instalações existentes do Microsoft 365 Apps para Grandes Empresas. Como Microsoft 365 Apps para Grandes Empresas instala Teams somente por usuário, consulte a seção Instalar ou atualizar o aplicativo Teams área de trabalho [na VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Usando Teams com instalação por computador e Microsoft 365 Apps para Grandes Empresas

Microsoft 365 Apps para Grandes Empresas não dá suporte a instalações por computador de Teams. Para usar a instalação por computador, você deve excluir Teams de Microsoft 365 Apps para Grandes Empresas. Consulte [Implantar o aplicativo Teams área](#deploy-the-teams-desktop-app-to-the-vm) de trabalho na VM e como excluir Teams [implantação](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) por meio Microsoft 365 Apps para Grandes Empresas seção.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Como excluir a implantação Teams por meio Microsoft 365 Apps para Grandes Empresas

Para saber mais sobre Teams e Microsoft 365 Apps para Grandes Empresas, confira Como excluir o Teams de novas instalações do [Microsoft 365 Apps para Grandes Empresas](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) [e usar Política de Grupo  para controlar a instalação do Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implantar o Teams da área de trabalho na VM

1. Baixe o Teams MSI que corresponde ao seu sistema operacional VDI VM usando um dos seguintes links:

    - [Versão de 32 bits](https://statics.teams.cdn.office.net/production-windows/1.5.00.11865/Teams_windows.msi)
    - [Versão de 64 bits](https://statics.teams.cdn.office.net/production-windows-x64/1.5.00.11865/Teams_windows_x64.msi)

    > [!NOTE]
    > Para nuvens governamentais, consulte Instalação em [massa Teams usando o MSI (Windows)](msi-deployment.md) para obter os links de download para os arquivos MSI.

    A versão mínima do Teams da área de trabalho necessária é a versão 1.3.00.4461. Não há suporte para a retenção de PSTN em versões anteriores.

2. Instale o MSI na VM VDI executando um dos seguintes comandos:

    - Instalação por usuário (padrão)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Esse processo é a instalação padrão, que instala Teams na pasta `%AppData%` do usuário. Nesse ponto, a configuração da imagem dourada está concluída.

        > [!IMPORTANT]
        > Teams funcionará corretamente com a instalação por usuário em uma configuração não persistente.

    - Instalação por computador

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Esse processo adiciona uma chave do Registro necessária ao computador que permite que o Teams instalador saiba que é uma instância de VDI.  Sem ele, o instalador falhará, informando: "Falha na instalação.  Não é possível instalar para todos os usuários quando um ambiente VDI não é detectado."

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Esse processo instala Teams `%ProgramFiles(x86)%` na pasta em um sistema operacional de 64 `%ProgramFiles%` bits e na pasta em um sistema operacional de 32 bits. Nesse ponto, a configuração da imagem dourada está concluída.

        > [!IMPORTANT]
        >  A instalação Teams por computador é necessária para configurações não persistentes.

        Quando a próxima sessão de logon interativo for iniciada, Teams iniciará e solicitará credenciais.

        > [!NOTE]
        > Esses exemplos também usam o `ALLUSERS=1` parâmetro. Quando você define esse parâmetro, **Teams Machine-Wide Instalador** aparece em Programas e  Recursos no **Painel de Controle** e em Aplicativos **&** recursos no **Windows Configurações** para todos os usuários do computador. Todos os usuários poderão desinstalar Teams se tiverem credenciais de administrador.
        >
        > É importante entender a diferença entre e `ALLUSERS=1` `ALLUSER=1`. O `ALLUSERS=1` parâmetro pode ser usado em ambientes não VDI e VDI, `ALLUSER=1` enquanto o parâmetro é usado somente em ambientes VDI para especificar uma instalação por computador.

3. Desinstale o MSI da VM VDI. Há duas maneiras de desinstalar Teams.

    - **Script do PowerShell**: você pode usar o script [do PowerShell](scripts/powershell-script-deployment-cleanup.md) de limpeza Teams implantação para desinstalar o Teams e remover a pasta Teams para um usuário. Execute o script para cada perfil de usuário no qual Teams foi instalado no computador.
    - **Linha de** comando: execute o seguinte comando.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Esse processo desinstala Teams da pasta `%ProgramFiles(x86)%` `%ProgramFiles%` ou pasta, dependendo do ambiente do sistema operacional.

## <a name="teams-on-vdi-performance-considerations"></a>Teams considerações de desempenho da VDI

Há uma variedade de configurações de configuração virtualizadas, cada uma com um foco diferente para otimização. Por exemplo, uma configuração pode se concentrar na densidade do usuário. Ao planejar, considere o seguinte para ajudar a otimizar sua configuração com base nas necessidades de carga de trabalho da sua organização.

- **Requisito mínimo**: algumas cargas de trabalho podem exigir uma configuração usando recursos que estão acima dos requisitos mínimos. Por exemplo, cargas de trabalho para desenvolvedores que usam aplicativos que exigem mais recursos de computação.
- **Dependências**: elas incluem dependências de infraestrutura, carga de trabalho e outras considerações ambientais fora do Teams da área de trabalho.
- **Recursos desabilitados na VDI**: Teams desabilita recursos com uso intensivo de GPU para VDI, o que pode ajudar a melhorar a utilização transitória da CPU. Os seguintes recursos estão desabilitados:
    - Teams css
    - Início automático do Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams na VDI com chamadas e reuniões

Além de chat e colaboração, Teams na VDI com chamadas e reuniões está disponível com plataformas de provedores de virtualização com suporte. Os recursos com suporte são baseados na pilha de mídia WebRTC e na implementação do provedor de virtualização. O diagrama a seguir fornece uma visão geral da arquitetura.

![Diagrama mostrando Teams arquitetura VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se você executar o Teams sem otimização de AV na VDI e usar recursos que ainda não têm suporte para otimização (como Dar e assumir o controle durante o compartilhamento de aplicativos), precisará definir políticas do provedor de virtualização para desativar Teams redirecionamento. Isso significa Teams sessões de mídia não serão otimizadas. Para obter etapas sobre como definir políticas para desativar Teams redirecionamento, entre em contato com seu provedor de virtualização.

### <a name="network-requirements"></a>Requisitos de rede

Recomendamos que você avalie seu ambiente para identificar quaisquer riscos e requisitos que possam influenciar sua implantação geral de voz e vídeo na nuvem. Use a [Skype for Business de Avaliação de](https://www.microsoft.com/download/details.aspx?id=53885) Rede para testar se sua rede está pronta para Teams.

Para saber mais sobre como preparar sua rede para Teams, consulte Preparar a rede da sua organização [para Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar do Skype for Business na VDI para o Teams na VDI

Se você estiver migrando do Skype for Business na VDI para o Teams na VDI, além das diferenças entre os dois aplicativos, haverá algumas diferenças quando a VDI também é implementada. Alguns recursos que atualmente não têm suporte no Teams VDI que estão Skype for Business VDI são os seguintes:

- Política por plataforma para desabilitar alguns recursos da AV na VDI
- Dar e assumir o controle durante o compartilhamento de aplicativos
- Compartilhamento de tela do chat sem áudio
- Envio e recebimento simultâneos de vídeo e compartilhamento de tela

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams no navegador Chrome versus Teams aplicativo da área de trabalho para VDI

Teams navegador Chrome não fornece uma substituição para o aplicativo da área de trabalho Teams para VDI com otimização av. A experiência de chat e colaboração funciona conforme o esperado. Quando a mídia é necessária, há algumas experiências que podem não atender às expectativas do usuário no navegador Chrome:

- A experiência de streaming de áudio e vídeo pode não ser ideal. Os usuários podem ter atrasos ou qualidade reduzida.
- As configurações do dispositivo não estão disponíveis nas configurações do navegador.
- O gerenciamento de dispositivos é tratado por meio do navegador e requer várias configurações nas configurações do site do navegador.
- As configurações do dispositivo também podem precisar ser definidas no Windows de dispositivos.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams na VDI com chat e colaboração

Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você poderá definir políticas de nível de usuário para desativar a funcionalidade de chamada e reunião Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e reunião

Você pode definir políticas usando o Teams de administração ou o PowerShell. São necessárias até algumas horas para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.

[**Políticas de chamada**](teams-calling-policy.md): Teams inclui a política de chamada **DisallowCalling** interna, na qual todos os recursos de chamada são desativados. Atribua **a política DisallowCalling** a todos os usuários em sua organização que usam Teams em um ambiente virtualizado.

[**Políticas de**](meeting-policies-overview.md) reunião: Teams inclui a política de reunião **AllOff** interna, na qual todos os recursos da reunião estão desativados. Atribua a **política AllOff** a todos os usuários em sua organização que usam Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Atribuir políticas usando o Teams de administração

Para atribuir a **política de chamada DisallowCalling** e a **política de reunião AllOff** a um usuário:

1. No painel de navegação à esquerda do Teams de administração, vá para **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1. Em **Política de chamada**, clique **em DisallowCalling**.
    2. Em **Política de Reunião**, clique **em AllOff**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. No painel de navegação esquerdo do Teams de administração, acesse Usuários **e, em** seguida, pesquise os usuários ou filtre a exibição para mostrar os usuários desejados.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique **no&#x2713;** (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. No painel de navegação esquerdo do Teams de administração, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **políticas** **voiceCalling** >  e clique **em DisallowCalling**.
    - Vá para **políticas** **MeetingsMeeting** >  e clique em **AllOff**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) `DisallowCalling` para atribuir a política de chamada a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOff` para atribuir a política de reunião a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar Teams VDI com chat e colaboração para otimizar Teams chamadas e reuniões

Se você tiver uma implementação existente do Teams na VDI com chat e colaboração em que você definiu políticas de nível de usuário para desativar a funcionalidade de chamada e reunião e estiver migrando para o Teams com otimização de AV, deverá definir políticas para ativar a funcionalidade de chamada e reunião para esses usuários Teams VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Definir políticas para ativar a funcionalidade de chamada e reunião

Você pode usar o Teams de administração ou o PowerShell para definir e atribuir políticas de chamada e reunião aos usuários. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente após algumas horas.

[**Políticas de chamada**](teams-calling-policy.md): políticas de chamada Teams controle quais recursos de chamada estão disponíveis para os usuários. Teams inclui a política interna **de chamada AllowCalling**, na qual todos os recursos de chamada estão ativados. Para ativar todos os recursos de chamada, atribua **a política AllowCalling** . Ou crie uma política de chamada personalizada para ativar os recursos de chamada desejados e atribuí-la aos usuários.

[**Políticas de**](meeting-policies-overview.md) reunião: as políticas de reunião Teams controlam os tipos de reuniões que os usuários podem criar e os recursos que estão disponíveis para os participantes da reunião agendados pelos usuários em sua organização. Teams inclui a política de reunião **AllOn** interna, na qual todos os recursos de reunião estão ativados. Para ativar todos os recursos de reunião, atribua a **política AllOn** . Ou crie uma política de reunião personalizada para ativar os recursos de reunião desejados e atribua a ela usuários.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Atribuir políticas usando o Teams de administração

Para atribuir a **política de chamada AllowCalling** e a **política de reunião AllOn** a um usuário:

1. No painel de navegação à esquerda do Teams de administração, vá para **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1. Em **Política de chamada**, clique **em AllowCalling**.
    2. Em **Política de Reunião**, clique **em AllOn**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. No painel de navegação esquerdo do Teams de administração, acesse Usuários **e, em** seguida, pesquise os usuários ou filtre a exibição para mostrar os usuários desejados.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique **no&#x2713;** (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. No painel de navegação esquerdo do Teams de administração, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **políticas** **voiceCalling** >  e clique **em AllowCalling**.
    - Vá para **políticas** **MeetingsMeeting** >  e clique em **AllOn**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) `AllowCalling` para atribuir a política de chamada a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOn` para atribuir a política de reunião a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Controlar o modo de fallback no Teams

Quando os usuários se conectam de um ponto de extremidade sem suporte, os usuários estão no modo de fallback, no qual a AV não é otimizada. Você pode desabilitar ou habilitar o modo de fallback definindo um dos seguintes valores do `DWORD` Registro:

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

Para desabilitar o modo de fallback, defina o valor como **1**. Para habilitar somente áudio, defina o valor **como 2**. Se o valor não estiver presente ou estiver definido como **0** (zero), o modo de fallback será habilitado.

Esse recurso está disponível Teams versão 1.3.00.13565 e posterior.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Desabilitar configurações de áudio e vídeo para VDI

Teams políticas de VDI estão disponíveis no Teams módulo. Essas políticas são ativas e impostas em ambientes VDI não otimizados.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> Isso é apenas para ambientes não otimizados.

### <a name="update-a-module-name"></a>Atualizar um nome de módulo

```PowerShell
Update-Module -Name MicrosoftTeams -AllowPrerelease

<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a>Definir políticas para limitar os recursos de chamada

Quando os usuários cuja política VDI `DisableCallsAndMeetings` está definida `$true` para entrar Teams na VDI, eles não podem:

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

Quando os usuários cuja política VDI `DisableAudioVideoInCallsAndMeetings` está definida `$true` para entrar Teams na VDI, eles:

- Pode compartilhar a tela do chat.
- Pode ingressar em uma reunião e compartilhar uma tela e mover o áudio para um telefone.
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

## <a name="known-issues-and-limitations"></a>Problemas conhecidos e limitações

### <a name="client-deployment-installation-and-setup"></a>Implantação, instalação e instalação do cliente

- Com a instalação por computador, Teams na VDI não é atualizada automaticamente da maneira que os clientes não VDI Teams são. Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção Instalar ou atualizar o aplicativo Teams área de trabalho na [VDI](#install-or-update-the-teams-desktop-app-on-vdi). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- Em ambientes citrix, se o usuário se desconectar da Máquina Virtual enquanto o Teams estiver em execução, as atualizações do Teams poderão fazer com que o usuário esteja em um estado não otimizado para AV quando se reconectar. Recomendamos que os usuários Teams antes de se desconectarem da Máquina Virtual citrix para evitar esse cenário.
- Teams deve ser implantado por usuário ou por computador. Não há suporte Teams implantação de aplicativos simultâneos por usuário e por computador. Para migrar de cada computador ou por usuário para um desses modos, siga o procedimento de desinstalação e reimplante para qualquer um dos modos.
- A Área de Trabalho Virtual do Azure não dá suporte macOS clientes baseados em Linux no momento.
- A opção de locatário rápido pode resultar em problemas relacionados à chamada na VDI, como o compartilhamento de tela não disponível. Reiniciar o cliente atenuará esses problemas.

### <a name="notifications"></a>Notificações

- A notificação de contagem de mensagens e a presença Windows barra de tarefas não tem suporte em um host Windows Server 2016 dados.

### <a name="calling-and-meetings"></a>Chamadas e reuniões

Não há suporte para os seguintes recursos de chamada e reunião:

- Qualquer funcionalidade de várias janelas, como as novas experiências de reunião ou qualquer funcionalidade que venha com a nova experiência de reunião
- Botões HID e controles DE LED entre o aplicativo Teams e dispositivos para Citrix e VMware
- Desfoque e efeitos da tela de fundo
- Funções de produtor e apresentador de eventos ao vivo e transmissão
- Location-Based LBR (Roteamento de Location-Based)
- Tom de toque de toque de chamada PSTN
- Áudio do sistema compartilhado/som do computador
- Bypass de mídia para Roteamento Direto
- Controle de zoom

> [!NOTE]
> Estamos trabalhando para adicionar recursos de chamada e reunião que estão disponíveis atualmente apenas em ambientes não VDI. Isso pode incluir mais controle de administrador sobre qualidade, cenários adicionais de compartilhamento de tela e recursos avançados adicionados recentemente ao Teams. Entre em contato Teams representante do Teams para saber mais sobre os recursos futuros.

A seguir estão os problemas conhecidos e as limitações para chamadas e reuniões:

- A interoperabilidade com Skype for Business é limitada a chamadas de áudio; não há nenhuma modalidade de vídeo.
- A resolução de fluxo de vídeo de entrada e saída é limitada à resolução de 720p.
- Há suporte para apenas um fluxo de vídeo de um fluxo de compartilhamento de tela ou câmera de entrada. Quando há um compartilhamento de tela de entrada, esse compartilhamento de tela é mostrado, em vez do vídeo do alto-falante dominante.
- Teams não alterna para usar o último dispositivo de áudio selecionado por um usuário, se o dispositivo estiver desconectado e, em seguida, reconectado.
- Eventos ao vivo não são otimizados.
- Compartilhamento de tela de saída:
  - Não há suporte para compartilhamento de aplicativos.
- Dê controle e controle:
  - Sem suporte durante um compartilhamento de tela ou sessão de compartilhamento de aplicativos.
  - Com suporte durante uma sessão PowerPoint de compartilhamento.

Para Teams problemas conhecidos que não estão relacionados à VDI, consulte Suporte [Teams em sua organização](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Solução de problemas

### <a name="troubleshoot-citrix-components"></a>Solucionar problemas de componentes do Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams falha ou a tela de Teams de entrada está em branco

Esse é um problema conhecido com o Citrix VDA versões 1906 e 1909. Para contornar esse problema, adicione o seguinte valor do `DWORD` Registro e defina-o como `204` (hexadecimal).

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

Em seguida, reinicie o VDA. Para saber mais, confira este artigo de suporte do Citrix, [solucionando problemas de otimização do HDX para Microsoft Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Tópicos relacionados

- [Instalação em Teams usando o Windows (MSI)](msi-deployment.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar Microsoft Teams na Área de Trabalho Virtual do Azure](/azure/virtual-desktop/teams-on-wvd)
