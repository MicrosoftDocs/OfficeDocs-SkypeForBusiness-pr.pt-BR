---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: serdars
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Saiba como executar o Microsoft Teams em um ambiente VDI (Infraestrutura de Área de Trabalho Virtualizada).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce78cfa86dfe562b33a892fbcc85a3946097eca6
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257352"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para Infraestrutura de Área de Trabalho Virtualizada

Este artigo descreve os requisitos e limitações para o uso Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é VDI?

Virtual Desktop Infrastructure (VDI) é uma tecnologia de virtualização que hospeda um sistema operacional da área de trabalho e aplicativos em um servidor centralizado em um data center. Isso permite uma experiência de área de trabalho totalmente personalizada para usuários com uma fonte centralizada totalmente segura e compatível.

Microsoft Teams em um ambiente virtualizado oferece suporte a chat e colaboração. E com as plataformas Desktop Virtual, Citrix e VMware do Azure, a funcionalidade de chamada e reunião também é suportada.

Teams em um ambiente virtualizado oferece suporte a várias configurações. Elas incluem modos VDI, dedicados, compartilhados, persistentes e não persistentes. Os recursos estão em desenvolvimento contínuo e são adicionados regularmente, e a funcionalidade será expandida nos próximos meses e anos.

Usar Teams em um ambiente virtualizado pode ser um pouco diferente de usar Teams em um ambiente não virtualizado. Por exemplo, alguns recursos avançados podem não estar disponíveis em um ambiente virtualizado, e a resolução de vídeo pode ser diferente.

Para garantir uma experiência de usuário ideal, siga as diretrizes neste artigo.

> [!Note]
> Para obter detalhes sobre Teams VDI em diferentes plataformas, [consulte Teams recursos por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams componentes VDI

Usar Teams em um ambiente virtualizado requer os seguintes componentes.

- **Agente de virtualização**: o gerenciador de recursos e conexões para o provedor de virtualização, como o Azure
- **Área de** trabalho virtual : a pilha da máquina virtual (VM) que executa Microsoft Teams
- **Cliente fino**: o ponto de extremidade com o que o usuário faz interface física
- **Teams da área de** trabalho : o Teams cliente da área de trabalho

## <a name="teams-on-vdi-requirements"></a>Teams requisitos VDI

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O Teams da área de trabalho foi validado com os principais provedores de soluções de virtualização. Com vários provedores de mercado, recomendamos que você consulte seu provedor de soluções de virtualização para garantir que você atender aos requisitos mínimos.
  
Atualmente, Teams em VDI com otimização de áudio/vídeo (AV) é certificada com a Área de Trabalho Virtual do Azure, Citrix e VMware. Revise as informações nesta seção para garantir que você atender a todos os requisitos para a funcionalidade adequada.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para Teams

As plataformas a seguir têm soluções de infraestrutura de área de trabalho virtual para Teams.

|Plataforma|Solução|
|----|---|
|![O logotipo que representa a Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Área de trabalho virtual do Azure</a> |
|![O logotipo que representa Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![O logotipo que representa a VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Área de trabalho virtual do Azure

A Área de Trabalho Virtual do Azure fornece otimização av para Teams em VDI. Para saber mais e requisitos e instalação, consulte [Use Teams no Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos do Citrix Virtual Apps and Desktops

O Citrix Virtual Apps and Desktops (anteriormente conhecido como XenApp e XenDesktop) fornece otimização av para Teams em VDI. Com o Citrix Virtual Apps and Desktops, Teams em VDI oferece suporte à funcionalidade de chamada e reunião, além de chat e colaboração.

Você pode baixar a versão mais recente do Citrix Virtual Apps and Desktops [no site de downloads do Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Você precisará entrar primeiro.) Os componentes necessários são agrupados no [aplicativo CWA (Citrix Workspace)](https://www.citrix.com/downloads/workspace-app/) e no VDA (Virtual Delivery Agent) por padrão. Não é necessário instalar componentes ou plug-ins adicionais no CWA ou no VDA.

Para saber mais sobre os requisitos de servidor e cliente mais recentes, [consulte este site do Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos de Espaço de Trabalho e Área de Trabalho do VMware Horizon

O VMware Horizon é uma plataforma moderna para entrega segura de desktops virtuais e aplicativos em toda a nuvem híbrida. Para oferecer uma ótima experiência do usuário final, o VMware Horizon fornece otimização de mídia para Teams. Essa otimização melhora a produtividade geral em áreas de trabalho virtuais e aplicativos e aprimora a experiência do usuário ao chamar e reunião usando Teams.

Você pode baixar a versão mais recente do VMware Horizon na [página Downloads do VMware.](https://customerconnect.vmware.com/downloads/#all_products) Os componentes de otimização de mídia necessários fazem parte do Agente do Horizonte e do Cliente horizon por padrão e não há necessidade de instalar qualquer plug-in adicional para usar o recurso de otimização para Teams.

Para obter os requisitos e instruções mais recentes sobre como configurar a otimização de mídia para Teams, consulte [este site VMware](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar ou atualizar o Teams da área de trabalho no VDI

Você pode implantar o Teams desktop para VDI usando uma instalação por máquina ou por usuário usando o pacote MSI. Decidir qual abordagem usar depende se você usa uma instalação persistente ou não persistente e as necessidades de funcionalidade associadas da sua organização.

Para uma instalação persistente dedicada, qualquer abordagem funcionaria. No entanto, para uma instalação não persistente, o Teams requer uma instalação por máquina para funcionar com eficiência. Consulte a [seção Configuração não persistente.](#non-persistent-setup)

Com a instalação por máquina, as atualizações automáticas são desabilitadas. Isso significa que, para atualizar o Teams, você deve desinstalar a versão atual para atualizar para uma versão mais recente. Com a instalação por usuário, as atualizações automáticas são habilitadas. Para a maioria das implantações VDI, recomendamos que você implante Teams usando a instalação por máquina.

Para atualizar para a versão Teams versão mais recente, comece com o procedimento de desinstalação seguido pela implantação Teams versão mais recente.

Para Teams otimização av em ambientes VDI funcione corretamente, o ponto de extremidade do cliente fino deve ter acesso à Internet. Se o acesso à Internet não estiver disponível no ponto de extremidade do cliente fino, a inicialização de otimização não será bem-sucedida. Isso significa que o usuário está em um estado de mídia não otimizado.

#### <a name="dedicated-persistent-setup"></a>Instalação persistente dedicada

Em uma instalação persistente dedicada, as alterações do sistema operacional local dos usuários são mantidas após o logoff dos usuários. Para a instalação persistente, Teams oferece suporte à instalação por usuário e por máquina.

A seguir está a configuração mínima de VM recomendada.

|Parâmetro  |Sistema operacional de estação de trabalho  |Sistema operacional do servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4,6 ou 8<br>É importante entender a configuração subjacente de acesso à memória não uniforme (NUMA) e configurar suas VMs de acordo.     |
|RAM     |   4 GB      | 512 a 1024 MB por usuário        |
|Armazenamento    | 8 GB        | 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Instalação não persistente

Em uma configuração não persistente, as alterações do sistema operacional local dos usuários não são mantidas depois que os usuários fazem logoff. Essas configurações são normalmente sessões compartilhadas com vários usuários. A configuração da VM varia com base no número de usuários e nos recursos de caixa física disponíveis.

Para uma configuração não persistente, o Teams da área de trabalho deve ser instalado por máquina na imagem dourada. (Para saber mais, consulte a seção Instalar ou atualizar o Teams [da área de trabalho na VDI.)](#install-or-update-the-teams-desktop-app-on-vdi) Isso garante um lançamento eficiente do aplicativo Teams durante uma sessão do usuário.

Usar Teams em uma configuração não persistente também requer um gerenciador de cache de perfil, para uma sincronização de dados Teams tempo de execução eficiente. A sincronização eficiente de dados garante que as informações específicas do usuário apropriadas (como dados, perfil ou configurações do usuário) são armazenadas em cache durante a sessão do usuário. Certifique-se de que os dados nessas duas pastas sejam sincronizados:<br>

- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Uma pasta roaming (ou, se você estiver usando redirecionamento de pasta, um gerenciador de cache) é necessária para garantir que o aplicativo Teams tenha os dados e arquivos de tempo de execução necessários para executar o aplicativo. Isso é necessário para atenuar problemas de latência de rede ou falhas de rede, o que poderia causar erros de aplicativo e uma experiência lenta devido a dados e arquivos indisponíveis.

Há uma variedade de soluções de gerenciador de cache disponíveis. Por exemplo, [FSLogix](/fslogix/overview). Consulte seu provedor de gerenciador de cache para obter instruções de configuração específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams lista de exclusão de conteúdo em cache para instalação não persistente

Exclua o seguinte da pasta Teams de cache, %appdata%/Microsoft/Teams. Excluir esses itens ajuda a reduzir o tamanho do cache do usuário para otimizar ainda mais sua configuração não persistente.

- .txt arquivos
- Pasta de pilha de mídia
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps para Grandes Empresas considerações

Considere o seguinte ao implantar Teams com Microsoft 365 Apps para Grandes Empresas na VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Novas implantações de Teams por meio Microsoft 365 Apps para Grandes Empresas

Antes de implantar Teams por Microsoft 365 Apps para Grandes Empresas, primeiro desinstale todos os aplicativos de Teams pré-existentes se eles foram implantados usando a instalação por máquina.

Teams por Microsoft 365 Apps para Grandes Empresas é instalado por usuário. Para saber mais, confira [a seção Instalar ou atualizar o Teams desktop na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams implantações por meio Microsoft 365 Apps para Grandes Empresas atualizações

Teams também está sendo adicionado às instalações existentes de Microsoft 365 Apps para Grandes Empresas. Como Microsoft 365 Apps para Grandes Empresas instala somente Teams por usuário, consulte a seção Instalar ou atualizar o Teams da área de trabalho [na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Usando Teams com instalação por máquina e Microsoft 365 Apps para Grandes Empresas

Microsoft 365 Apps para Grandes Empresas não dá suporte a instalações por máquina de Teams. Para usar a instalação por máquina, você deve excluir Teams de Microsoft 365 Apps para Grandes Empresas. Consulte [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and How to exclude Teams [deployment through Microsoft 365 Apps para Grandes Empresas](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Como excluir Teams implantação por meio Microsoft 365 Apps para Grandes Empresas

Para saber mais sobre Teams e Microsoft 365 Apps para Grandes Empresas, consulte Como excluir o Teams de novas instalações do [Microsoft 365 Apps para Grandes Empresas](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) e Usar a Política de Grupo para controlar a instalação [de Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implantar o Teams da área de trabalho na VM

1. Baixe o Teams MSI que corresponde ao seu sistema operacional VDI VM usando um dos seguintes links:

    - [Versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Para nuvens do governo, consulte [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.

    A versão mínima do Teams da área de trabalho necessária é a versão 1.3.00.4461. (A espera PSTN não é suportada em versões anteriores.)

2. Instale o MSI na VM VDI executando um dos seguintes comandos:

    - Instalação por usuário (padrão)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Esse processo é a instalação padrão, que instala Teams na pasta de usuário %AppData%. Nesse ponto, a configuração da imagem dourada está concluída. Teams funcionará corretamente com a instalação por usuário em uma instalação não persistente.

    - Instalação por máquina

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Esse processo adiciona uma chave de registro necessária ao computador que permite que o Teams saiba que é uma instância VDI.  Sem ele, o instalador falhará, informando: "A instalação falhou.  Não é possível instalar para todos os usuários quando um ambiente VDI não é detectado."

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Esse processo instala Teams na pasta Arquivos de Programas (x86) em um sistema operacional de 64 bits e na pasta Arquivos de Programas em um sistema operacional de 32 bits. Nesse ponto, a configuração da imagem dourada está concluída. A instalação Teams por máquina é necessária para configurações não persistentes.

        A próxima sessão de logon interativo inicia o Teams e pede credenciais.

        > [!NOTE]
        > Esses exemplos também usam o **parâmetro ALLUSERS=1.** Quando você define este parâmetro, o Instalador de Todo o Computador do Teams aparece em Programas e recursos no Painel de Controle e em Aplicativos e Recursos nas Configurações do Windows para todos os usuários do computador. Todos os usuários podem desinstalar Teams se eles têm credenciais de administrador.
        É importante entender a diferença entre **ALLUSERS=1** e **ALLUSER=1**. O **parâmetro ALLUSERS=1** pode ser usado em ambientes que não sejam VDI e VDI, enquanto o parâmetro **ALLUSER=1** é usado somente em ambientes VDI para especificar uma instalação por máquina.

3. Desinstale o MSI da VM VDI. Há duas maneiras de desinstalar Teams.

    - Script do PowerShell: você pode usar esse [script do PowerShell](scripts/powershell-script-deployment-cleanup.md) para desinstalar Teams e remover a pasta Teams para um usuário. Execute o script para cada perfil de usuário no qual Teams foi instalado no computador.
    - Linha de comando: Execute o seguinte comando.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Esse processo desinstala Teams da pasta Arquivos de Programas (x86) ou da pasta Arquivos de Programas, dependendo do ambiente do sistema operacional.

## <a name="teams-on-vdi-performance-considerations"></a>Teams considerações sobre o desempenho da VDI

Há uma variedade de configurações de configuração virtualizadas, cada uma com um foco diferente para otimização. Por exemplo, uma configuração pode se concentrar na densidade do usuário. Ao planejar, considere o seguinte para ajudar a otimizar sua instalação com base nas necessidades de carga de trabalho da sua organização.

- Requisito mínimo: Algumas cargas de trabalho podem exigir uma instalação usando recursos que estão acima dos requisitos mínimos. Por exemplo, cargas de trabalho para desenvolvedores que usam aplicativos que exigem mais recursos de computação.
- Dependências: elas incluem dependências de infraestrutura, carga de trabalho e outras considerações ambientais fora do Teams da área de trabalho.
- Recursos desabilitados na VDI: Teams desabilita recursos intensivos de GPU para VDI, o que pode ajudar a melhorar a utilização transitória da CPU. Os seguintes recursos estão desabilitados:
    - Teams css
    - Início automático giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams VDI com chamada e reuniões

Além de chat e colaboração, o Teams em VDI com chamada e reuniões está disponível com plataformas de provedores de virtualização com suporte. Os recursos suportados são baseados na pilha de mídia WebRTC e na implementação do provedor de virtualização. O diagrama a seguir fornece uma visão geral da arquitetura.

![Diagrama mostrando Teams na arquitetura VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se você atualmente executar o Teams sem otimização de AV na VDI e usar recursos que ainda não são suportados para otimização (como Dar e assumir controle ao compartilhar aplicativos), você terá que definir políticas de provedor de virtualização para desativar Teams redirecionamento. Isso significa que Teams sessões de mídia não serão otimizadas. Para saber mais sobre como definir políticas para desativar Teams redirecionamento, entre em contato com seu provedor de virtualização.

### <a name="network-requirements"></a>Requisitos de rede

Recomendamos que você avalie seu ambiente para identificar quaisquer riscos e requisitos que possam influenciar sua implantação geral de voz na nuvem e vídeo. Use a [Skype for Business de Avaliação de Rede](https://www.microsoft.com/download/details.aspx?id=53885) para testar se sua rede está pronta para Teams.

Para saber mais sobre como preparar sua rede para Teams, consulte Prepare your [organization's network for Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar do Skype for Business VDI para o Teams VDI

Se você estiver migrando do Skype for Business VDI para o Teams VDI, além das diferenças entre os dois aplicativos, há algumas diferenças quando a VDI também é implementada. Alguns recursos que atualmente não são suportados no Teams VDI que estão no Skype for Business VDI são os seguinte:

- Política por plataforma para desabilitar alguns recursos av no VDI
- Dar e assumir controle ao compartilhar aplicativos
- Compartilhamento de tela do chat sem áudio
- Envio e recebimento simultâneos de vídeo e compartilhamento de tela

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams navegador Chrome versus Teams desktop para VDI

Teams no navegador Chrome não fornece uma substituição para o aplicativo de área de trabalho Teams para VDI com otimização av. A experiência de chat e colaboração funciona conforme esperado. Quando a mídia é necessária, há algumas experiências que podem não atender às expectativas do usuário no navegador Chrome:

- A experiência de streaming de áudio e vídeo pode não ser ideal. Os usuários podem ter atrasos ou qualidade reduzida.
- As configurações do dispositivo não estão disponíveis nas configurações do navegador.
- O gerenciamento de dispositivos é manipulado pelo navegador e requer várias configurações nas configurações do site do navegador.
- As configurações do dispositivo também podem precisar ser definidas no Windows de dispositivos.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams em VDI com chat e colaboração

Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você pode definir políticas no nível do usuário para desativar a funcionalidade de chamada e reunião em Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e reunião

Você pode definir políticas usando o centro de administração Microsoft Teams ou o PowerShell. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.

[**Políticas de chamada**](teams-calling-policy.md): Teams inclui a política de chamada DisallowCalling interna, na qual todos os recursos de chamada estão desligados. Atribua a política DisallowCalling a todos os usuários da sua organização que usam Teams em um ambiente virtualizado.

[**Políticas de**](meeting-policies-overview.md)reunião : Teams inclui a política de reunião AllOff interna, na qual todos os recursos de reunião estão desligados. Atribua a política AllOff a todos os usuários da sua organização que usam Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o Microsoft Teams de administração

Para atribuir a política de chamada DisallowCalling e a política de reunião AllOff a um usuário:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1. Em **Política de Chamada,** clique **em DisallowCalling**.
    2. Em **Política de Reunião,** clique **em AllOff**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **Políticas de Chamada**  >  **de** Voz e clique **em DisallowCalling**.
    - Vá para **Políticas de Reunião** de  >  **Reuniões** e clique em **AllOff**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada DisallowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamadas, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOff a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar Teams VDI com chat e colaboração para otimizar Teams com chamada e reuniões

Se você tiver uma implementação existente do Teams em VDI com chat e colaboração no qual você definiu políticas no nível do usuário para desativar a funcionalidade de chamada e reunião e está migrando para o Teams com otimização de AV, você deve definir políticas para ativar a funcionalidade de chamada e reunião para esses Teams em usuários VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Definir políticas para ativar a funcionalidade de chamada e reunião

Você pode usar o Microsoft Teams de administração ou o PowerShell para definir e atribuir políticas de chamada e reunião aos seus usuários. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente após algumas horas.

[**Políticas de chamada:**](teams-calling-policy.md)chamar políticas em Teams controle quais recursos de chamada estão disponíveis para os usuários. Teams inclui a política interna de chamada AllowCalling, na qual todos os recursos de chamada estão ativas. Para ativar todos os recursos de chamada, atribua a política AllowCalling. Ou crie uma política de chamada personalizada para ativar os recursos de chamada que você deseja e atribuí-la aos usuários.

[**Políticas de**](meeting-policies-overview.md)reunião : as políticas de reunião em Teams controlam os tipos de reuniões que os usuários podem criar e os recursos que estão disponíveis para os participantes da reunião agendados pelos usuários em sua organização. Teams inclui a política de reunião AllOn interna, na qual todos os recursos de reunião estão ativas. Para ativar todos os recursos de reunião, atribua a política AllOn. Ou crie uma política de reunião personalizada para ativar os recursos de reunião que você deseja e atribuí-la aos usuários.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o Microsoft Teams de administração

Para atribuir a política de chamada AllowCalling e a política de reunião AllOn a um usuário:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1. Em **Política de Chamada,** clique **em AllowCalling**.
    2. Em **Política de Reunião,** clique **em AllOn**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique na **&#x2713;** (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **Políticas de Chamada**  >  **de** Voz e clique **em AllowCalling**.
    - Vá para **Políticas de Reunião** de  >  **Reuniões** e clique em **AllOn**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada AllowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamadas, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOn a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Controlar o modo de fallback Teams

Quando os usuários se conectam de um ponto de extremidade sem suporte, os usuários estão no modo de fallback, no qual a AV não é otimizada. Você pode desabilitar ou habilitar o modo de fallback definindo um dos seguintes valores DWORD do Registro:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Para desabilitar o modo de fallback, de definir o valor **como 1**. Para habilitar somente áudio, de definir o valor como **2**. Se o valor não estiver presente ou estiver definido como **0** (zero), o modo de fallback será habilitado.

Esse recurso está disponível Teams versão 1.3.00.13565 e posterior.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Desabilitar configurações de áudio e vídeo para VDI

Teams VDI estão disponíveis no módulo Microsoft Teams. Essas políticas são ativas e impostas em ambientes VDI não otimizados.

- New-CsTeamsVdiPolicy  
- Grant-CsTeamsVdiPolicy
- Remove-CsTeamsVdiPolicy
- Set-CsTeamsVdiPolicy

> [!NOTE]
> Isso é apenas para ambientes não otimizados.

### <a name="update-a-module-name"></a>Atualizar um nome de módulo

update-Module -Name MicrosoftTeams -AllowPrerelease

```PowerShell
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

### <a name="set-policies-to-limit-calling-features"></a>Definir políticas para limitar recursos de chamada

Quando os usuários com essa configuração de Política VDI -DisableCallsAndMeetings $true entrar no Teams no VDI, eles não poderão:

- Fazer chamadas.
- Participe de reuniões.
- Faça um compartilhamento de tela do chat.

Todos os tipos de chamada devem ser desabilitados.

> [!NOTE]
> Isso é apenas para ambientes não otimizados.

```PowerShell
#>
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false
<# Assign Policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<#
Show all Policies  
#>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
<#
```

Quando os usuários com a configuração de Política VDI -DisableAudioVideoInCallsAndMeetings $true entrar no Teams VDI, eles poderão:

- Faça um compartilhamento de tela do chat.
- Participe de uma reunião e compartilhe uma tela. Mova o áudio para um telefone.
- Os usuários não devem ser capazes de fazer uma chamada de áudio e vídeo de pessoa para pessoa a partir da VDI.

> [!NOTE]
> Isso é apenas para ambientes não otimizados.

```powershell
#>
$PolName = "DisableCallsAndMeetingsAV"
New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<# ## Cleanup afterwards #>
$cleanup = $false
if($cleanup){
    "Doing cleanup"
    # de-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
    # remove Policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>Problemas conhecidos e limitações

### <a name="client-deployment-installation-and-setup"></a>Implantação, instalação e instalação do cliente

- Com a instalação por máquina, Teams na VDI não é atualizada automaticamente da maneira que os clientes que não Teams VDI são. Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção Instalar ou atualizar o Teams da área de trabalho [na VDI.](#install-or-update-the-teams-desktop-app-on-vdi) Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- Em ambientes Citrix, se o usuário se desconectar da Máquina Virtual enquanto o Teams está em execução, as atualizações Teams podem fazer com que o usuário esteja em um estado não otimizado para AV quando se reconectar. Recomendamos que os usuários Teams antes de se desconectar da Máquina Virtual citrix para evitar esse cenário.
- Teams deve ser implantado por usuário ou por máquina. Não há suporte Teams implantação de Teams para usuários simultâneos e por máquina. Para migrar de cada máquina ou por usuário para um desses modos, siga o procedimento de desinstalação e reimplante para ambos os modos.
- A Área de Trabalho Virtual do Azure não dá suporte a clientes baseados em macOS e Linux no momento.
- A opção de locatário rápido pode resultar em problemas relacionados a chamada na VDI, como compartilhamento de tela não disponível. Reiniciar o cliente atenua esses problemas.

### <a name="calling-and-meetings"></a>Chamada e reuniões

Os seguintes recursos de chamada e reunião não são suportados:

- Qualquer funcionalidade de várias janelas, como as novas experiências de reunião ou qualquer funcionalidade que venha com a nova experiência de reunião
- Serviços de emergência aprimorados
- Botões HID e controles DE LED entre o aplicativo Teams e dispositivos
- Desfoque e efeitos em segundo plano
- Funções de apresentador e produtor de eventos ao vivo e transmissão
- Location-Based Roteamento (LBR)
- Tom de retorno de toque de chamada PSTN
- Som de áudio/computador do sistema compartilhado
- Bypass de mídia para Roteamento Direto
- Controle zoom

> [!NOTE]
> Estamos trabalhando na adição de recursos de chamada e reunião que estão disponíveis apenas em ambientes que não sejam VDI. Isso pode incluir mais controle de administrador sobre qualidade, cenários adicionais de compartilhamento de tela e recursos avançados adicionados recentemente Teams. Entre em contato Teams representante do Teams para saber mais sobre os recursos futuros.

A seguir estão os problemas conhecidos e limitações de chamada e reuniões:

- A interoperabilidade com Skype for Business está limitada a chamadas de áudio; não há modalidade de vídeo.
- A resolução de fluxo de vídeo de entrada e saída é limitada à resolução de 720p.
- Há suporte para apenas um fluxo de vídeo de uma câmera de entrada ou de um fluxo de compartilhamento de tela. Quando há um compartilhamento de tela de entrada, esse compartilhamento de tela é mostrado, em vez do vídeo do alto-falante dominante.
- Teams alternar para usar o último dispositivo de áudio que um usuário selecionou, se o dispositivo estiver desconectado e, em seguida, reconectado.
- Os eventos ao vivo não são otimizados.
- Compartilhamento de tela de saída:
    - Não há suporte para compartilhamento de aplicativos.
- Dê controle e controle:
    - Não há suporte durante uma sessão de compartilhamento de tela ou de aplicativo.
    - Suportado durante uma sessão de PowerPoint de compartilhamento.

Para Teams problemas conhecidos que não estão relacionados à VDI, consulte [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Solução de problemas

### <a name="troubleshoot-citrix-components"></a>Solucionar problemas de componentes do Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams falha ou a tela de Teams de entrar está em branco

Esse é um problema conhecido com o Citrix VDA versões 1906 e 1909. Para resolver esse problema, adicione o seguinte valor DWORD do Registro e desmarca-o como 204 (hexadecimal).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Em seguida, reinicie o VDA. Para saber mais, confira este artigo de suporte do Citrix, [Solucionando problemas de otimização HDX para Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Microsoft Teams usando MSI](msi-deployment.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar Microsoft Teams na área de trabalho virtual do Azure](/azure/virtual-desktop/teams-on-wvd)
