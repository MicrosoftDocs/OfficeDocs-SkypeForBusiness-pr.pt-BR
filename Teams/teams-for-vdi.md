---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Saiba como executar o Microsoft Teams em um ambiente VDI (Infraestrutura de Área de Trabalho Virtualizada).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7262cc77310a9ea198a51af720e6e5117a72111
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874467"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para Infraestrutura de Área de Trabalho Virtualizada

Este artigo descreve os requisitos e limitações para usar o Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é VDI?

Virtual Desktop Infrastructure (VDI) é uma tecnologia de virtualização que hospeda um sistema operacional da área de trabalho e aplicativos em um servidor centralizado em um data center. Isso permite uma experiência de área de trabalho totalmente personalizada para usuários com uma fonte centralizada totalmente segura e compatível.

O Microsoft Teams em um ambiente virtualizado oferece suporte a chat e colaboração. E com as plataformas Windows Virtual Desktop, Citrix e VMware, a funcionalidade de chamada e reunião também é suportada.

O Teams em um ambiente virtualizado dá suporte a várias configurações. Elas incluem modos VDI, dedicados, compartilhados, persistentes e não persistentes. Os recursos estão em desenvolvimento contínuo e são adicionados regularmente, e a funcionalidade será expandida nos próximos meses e anos.

Usar o Teams em um ambiente virtualizado pode ser um pouco diferente de usar o Teams em um ambiente não virtualizado. Por exemplo, alguns recursos avançados podem não estar disponíveis em um ambiente virtualizado, e a resolução de vídeo pode ser diferente.

Para garantir uma experiência de usuário ideal, siga as diretrizes neste artigo.

> [!Note]
> Para obter detalhes sobre a VDI do Teams em diferentes plataformas, consulte [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams em componentes VDI

O uso do Teams em um ambiente virtualizado requer os seguintes componentes.

- **Agente de virtualização**: o gerenciador de recursos e conexões para o provedor de virtualização, como o Azure
- **Área de** trabalho virtual : a pilha de máquina virtual (VM) que executa o Microsoft Teams
- **Cliente fino**: o ponto de extremidade com o que o usuário faz interface física
- **Aplicativo da área de** trabalho do Teams : o aplicativo cliente da área de trabalho do Teams

## <a name="teams-on-vdi-requirements"></a>Teams em requisitos de VDI

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O aplicativo de área de trabalho do Teams foi validado com os principais provedores de soluções de virtualização. Com vários provedores de mercado, recomendamos que você consulte seu provedor de soluções de virtualização para garantir que você atender aos requisitos mínimos.
  
Atualmente, o Teams na VDI com otimização de áudio/vídeo (AV) é certificado com a Área de Trabalho Virtual do Windows, Citrix e VMware. Revise as informações nesta seção para garantir que você atender a todos os requisitos para a funcionalidade adequada.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para o Teams

As plataformas a seguir têm soluções de infraestrutura de área de trabalho virtual para o Teams.

|Plataforma|Solução|
|----|---|
|![O logotipo que representa a Microsoft](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Área de trabalho virtual do Windows</a> |
|![O logotipo que representa Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![O logotipo que representa a VMware](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Área de trabalho virtual do Windows

A Área de Trabalho Virtual do Windows fornece otimização av para o Teams no VDI. Para saber mais e requisitos e instalação, consulte [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos do Citrix Virtual Apps and Desktops

O Citrix Virtual Apps and Desktops (anteriormente conhecido como XenApp e XenDesktop) fornece otimização de AV para o Teams na VDI. Com o Citrix Virtual Apps and Desktops, o Teams na VDI oferece suporte à funcionalidade de chamada e reunião, além de chat e colaboração.

Você pode baixar a versão mais recente do Citrix Virtual Apps and Desktops [no site de downloads do Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Você precisará entrar primeiro.) Os componentes necessários são agrupados no [aplicativo CWA (Citrix Workspace)](https://www.citrix.com/downloads/workspace-app/) e no VDA (Virtual Delivery Agent) por padrão. Não é necessário instalar componentes ou plug-ins adicionais no CWA ou no VDA.

Para saber mais sobre os requisitos de servidor e cliente mais recentes, [consulte este site do Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos de Espaço de Trabalho e Área de Trabalho do VMware Horizon

O VMware Horizon é uma plataforma moderna para entrega segura de desktops virtuais e aplicativos em toda a nuvem híbrida. Para oferecer uma ótima experiência do usuário final, o VMware Horizon fornece otimização de mídia para o Teams. Essa otimização melhora a produtividade geral em áreas de trabalho virtuais e aplicativos e aprimora a experiência do usuário ao chamar e reunir usando o Teams.

Você pode baixar a versão mais recente do VMware Horizon na [página Downloads do VMware.](https://my.vmware.com/web/vmware/downloads/#all_products) Os componentes de otimização de mídia necessários fazem parte do Agente do Horizonte e do Cliente horizon por padrão e não há necessidade de instalar qualquer plug-in adicional para usar o recurso de otimização para o Teams.

Para obter os requisitos e instruções mais recentes sobre como configurar a otimização de mídia para o Teams, consulte [este site da VMware](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar ou atualizar o aplicativo de área de trabalho do Teams no VDI

Você pode implantar o aplicativo de área de trabalho do Teams para VDI usando uma instalação por máquina ou por usuário usando o pacote MSI. Decidir qual abordagem usar depende se você usa uma instalação persistente ou não persistente e as necessidades de funcionalidade associadas da sua organização.

Para uma instalação persistente dedicada, qualquer abordagem funcionaria. No entanto, para uma instalação não persistente, o Teams requer uma instalação por máquina para funcionar com eficiência. Consulte a [seção Configuração não persistente.](#non-persistent-setup)

Com a instalação por máquina, as atualizações automáticas são desabilitadas. Isso significa que, para atualizar o aplicativo do Teams, você deve desinstalar a versão atual para atualizar para uma versão mais recente. Com a instalação por usuário, as atualizações automáticas são habilitadas. Para a maioria das implantações VDI, recomendamos implantar o Teams usando a instalação por máquina.

Para atualizar para a versão mais recente do Teams, comece com o procedimento de desinstalação seguido pela implantação de versão mais recente do Teams.

Para que a otimização do Teams AV em ambientes VDI funcione corretamente, o ponto de extremidade do cliente fino deve ter acesso à Internet. Se o acesso à Internet não estiver disponível no ponto de extremidade do cliente fino, a inicialização de otimização não será bem-sucedida. Isso significa que o usuário está em um estado de mídia não otimizado.

#### <a name="dedicated-persistent-setup"></a>Instalação persistente dedicada

Em uma instalação persistente dedicada, as alterações do sistema operacional local dos usuários são mantidas após o logoff dos usuários. Para a instalação persistente, o Teams oferece suporte à instalação por usuário e por máquina.

A seguir está a configuração mínima de VM recomendada.

|Parâmetro  |Sistema operacional de estação de trabalho  |Sistema operacional do servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4,6 ou 8<br>É importante entender a configuração subjacente de acesso à memória não uniforme (NUMA) e configurar suas VMs de acordo.     |
|RAM     |   4 GB      | 512 a 1024 MB por usuário        |
|Armazenamento    | 8 GB        | 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Instalação não persistente

Em uma configuração não persistente, as alterações do sistema operacional local dos usuários não são mantidas depois que os usuários fazem logoff. Essas configurações são normalmente sessões compartilhadas com vários usuários. A configuração da VM varia com base no número de usuários e nos recursos de caixa física disponíveis.

Para uma configuração não persistente, o aplicativo de área de trabalho do Teams deve ser instalado por máquina na imagem dourada. (Para saber mais, consulte a seção Instalar ou atualizar o aplicativo de área de [trabalho do Teams na VDI.)](#install-or-update-the-teams-desktop-app-on-vdi) Isso garante um lançamento eficiente do aplicativo Teams durante uma sessão do usuário.

O uso do Teams em uma configuração não persistente também requer um gerenciador de cache de perfil, para uma sincronização eficiente de dados de tempo de execução do Teams. A sincronização eficiente de dados garante que as informações específicas do usuário apropriadas (como dados, perfil ou configurações do usuário) são armazenadas em cache durante a sessão do usuário. Certifique-se de que os dados nessas duas pastas sejam sincronizados:<br>
- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Uma pasta de roaming (ou, se você estiver usando redirecionamento de pasta, um gerenciador de cache) é necessária para garantir que o aplicativo teams tenha os dados e arquivos de tempo de execução necessários para executar o aplicativo. Isso é necessário para atenuar problemas de latência de rede ou falhas de rede, o que poderia causar erros de aplicativo e uma experiência lenta devido a dados e arquivos indisponíveis.

Há uma variedade de soluções de gerenciador de cache disponíveis. Por exemplo, [FSLogix](/fslogix/overview). Consulte seu provedor de gerenciador de cache para obter instruções de configuração específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Lista de exclusão de conteúdo em cache do Teams para instalação não persistente

Exclua o seguinte da pasta de cache do Teams, %appdata%/Microsoft/Teams. Excluir esses itens ajuda a reduzir o tamanho do cache do usuário para otimizar ainda mais sua configuração não persistente.

- Arquivos .txt
- Pasta de pilha de mídia
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps para considerações corporativas

Considere o seguinte ao implantar o Teams com o Microsoft 365 Apps para empresas no VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Novas implantações do Teams por meio do Microsoft 365 Apps para empresas

Antes de implantar o Teams por meio de Aplicativos do Microsoft 365 para empresas, primeiro desinstale todos os aplicativos do Teams pré-existentes se eles foram implantados usando a instalação por máquina.

O Teams por meio do Microsoft 365 Apps para empresas é instalado por usuário. Para saber mais, confira [a seção Instalar ou atualizar o aplicativo da área de trabalho do Teams na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Implantações do Teams por meio do Microsoft 365 Apps para atualizações corporativas

O Teams também está sendo adicionado às instalações existentes do Microsoft 365 Apps para empresas. Como o Microsoft 365 Apps para empresas instala apenas o Teams por usuário, consulte a seção Instalar ou atualizar o aplicativo de área de trabalho do [Teams na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Usando o Teams com a instalação por máquina e o Microsoft 365 Apps para empresas

O Microsoft 365 Apps para empresas não dá suporte a instalações por máquina do Teams. Para usar a instalação por máquina, você deve excluir o Teams do Microsoft 365 Apps para empresas. Consulte As [seções Implantar o aplicativo de área](#deploy-the-teams-desktop-app-to-the-vm) de trabalho do Teams na VM e Como excluir a implantação do Teams por meio de aplicativos do Microsoft [365 para empresas.](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Como excluir a implantação do Teams por meio do Microsoft 365 Apps para empresas

Para saber mais sobre o Teams e o Microsoft 365 Apps para empresas, consulte Como excluir o Teams de novas instalações do [Microsoft 365 Apps para](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) empresas e Usar Política de Grupo para controlar a instalação do [Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implantar o aplicativo de área de trabalho do Teams na VM

1. Baixe o pacote MSI do Teams que corresponde ao seu sistema operacional VDI VM usando um dos seguintes links:

    - [Versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Para nuvens do governo, consulte [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.

    A versão mínima do aplicativo de área de trabalho do Teams necessária é a versão 1.3.00.4461. (A espera PSTN não é suportada em versões anteriores.)

2. Instale o MSI na VM VDI executando um dos seguintes comandos:

    - Instalação por usuário (padrão)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Esse processo é a instalação padrão, que instala o Teams na pasta de usuário %AppData%. Nesse ponto, a configuração da imagem dourada está concluída. O Teams não funcionará corretamente com a instalação por usuário em uma instalação não persistente.

    - Instalação por máquina

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Esse processo instala o Teams na pasta Arquivos de Programas (x86) em um sistema operacional de 64 bits e na pasta Arquivos de Programas em um sistema operacional de 32 bits. Nesse ponto, a configuração da imagem dourada está concluída. A instalação do Teams por máquina é necessária para configurações não persistentes.

        A próxima sessão de logon interativo inicia o Teams e pede credenciais.

        > [!NOTE]
        > Esses exemplos também usam o **parâmetro ALLUSERS=1.** Quando você define este parâmetro, o Instalador de Todo o Computador do Teams aparece em Programas e recursos no Painel de Controle e em Aplicativos e Recursos nas Configurações do Windows para todos os usuários do computador. Todos os usuários podem desinstalar o Teams se eles têm credenciais de administrador.
        É importante entender a diferença entre **ALLUSERS=1** e **ALLUSER=1**. O **parâmetro ALLUSERS=1** pode ser usado em ambientes que não sejam VDI e VDI, enquanto o parâmetro **ALLUSER=1** é usado somente em ambientes VDI para especificar uma instalação por máquina.

3. Desinstale o MSI da VM VDI. Há duas maneiras de desinstalar o Teams.

    - Script do PowerShell: você pode usar [esse script do PowerShell](scripts/powershell-script-deployment-cleanup.md) para desinstalar o Teams e remover a pasta do Teams para um usuário. Execute o script para cada perfil de usuário no qual o Teams foi instalado no computador.
    - Linha de comando: Execute o seguinte comando.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Esse processo desinstala o Teams da pasta Arquivos de Programas (x86) ou da pasta Arquivos de Programas, dependendo do ambiente do sistema operacional.

## <a name="teams-on-vdi-performance-considerations"></a>Considerações sobre o desempenho do Teams em VDI

Há uma variedade de configurações de configuração virtualizadas, cada uma com um foco diferente para otimização. Por exemplo, uma configuração pode se concentrar na densidade do usuário. Ao planejar, considere o seguinte para ajudar a otimizar sua instalação com base nas necessidades de carga de trabalho da sua organização.

- Requisito mínimo: Algumas cargas de trabalho podem exigir uma instalação usando recursos que estão acima dos requisitos mínimos. Por exemplo, cargas de trabalho para desenvolvedores que usam aplicativos que exigem mais recursos de computação.
- Dependências: elas incluem dependências de infraestrutura, carga de trabalho e outras considerações ambientais fora do aplicativo de área de trabalho do Teams.
- Recursos desabilitados no VDI: o Teams desabilita os recursos intensivos de GPU para VDI, o que pode ajudar a melhorar a utilização transitória da CPU. Os seguintes recursos estão desabilitados:
    - Animação CSS do Teams
    - Início automático giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Equipes na VDI com chamada e reuniões

Além de chat e colaboração, o Teams na VDI com chamada e reuniões está disponível com plataformas de provedores de virtualização com suporte. Os recursos suportados são baseados na pilha de mídia WebRTC e na implementação do provedor de virtualização. O diagrama a seguir fornece uma visão geral da arquitetura.

![Diagrama mostrando o Teams na arquitetura VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se você atualmente executar o Teams sem otimização de AV na VDI e usar recursos que ainda não são suportados para otimização (como Dar e assumir controle ao compartilhar aplicativos), você terá que definir políticas de provedor de virtualização para desativar o redirecionamento do Teams. Isso significa que as sessões de mídia do Teams não serão otimizadas. Para saber mais sobre como definir políticas para desativar o redirecionamento do Teams, entre em contato com seu provedor de virtualização.

### <a name="network-requirements"></a>Requisitos de rede

Recomendamos que você avalie seu ambiente para identificar quaisquer riscos e requisitos que possam influenciar sua implantação geral de voz na nuvem e vídeo. Use a [Ferramenta de Avaliação de Rede](https://www.microsoft.com/download/details.aspx?id=53885) do Skype for Business para testar se sua rede está pronta para o Teams.

Para saber mais sobre como preparar sua rede para o Teams, consulte [Prepare your organization's network for Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar do Skype for Business no VDI para o Teams na VDI

Se você estiver migrando do Skype for Business no VDI para o Teams na VDI, além das diferenças entre os dois aplicativos, há algumas diferenças quando a VDI também é implementada. Alguns recursos que atualmente não são suportados na VDI do Teams que estão no VDI do Skype for Business são os seguinte:

- Política por plataforma para desabilitar alguns recursos av no VDI
- Dar e assumir controle ao compartilhar aplicativos
- Compartilhamento de tela do chat sem áudio
- Envio e recebimento simultâneos de vídeo e compartilhamento de tela

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams no navegador Chrome versus aplicativo de área de trabalho do Teams para VDI

O navegador teams no Chrome não fornece uma substituição para o aplicativo de área de trabalho do Teams para VDI com otimização av. A experiência de chat e colaboração funciona conforme esperado. Quando a mídia é necessária, há algumas experiências que podem não atender às expectativas do usuário no navegador Chrome:

- A experiência de streaming de áudio e vídeo pode não ser ideal. Os usuários podem ter atrasos ou qualidade reduzida.
- As configurações do dispositivo não estão disponíveis nas configurações do navegador.
- O gerenciamento de dispositivos é manipulado pelo navegador e requer várias configurações nas configurações do site do navegador.
- As configurações do dispositivo também podem precisar ser definidas no gerenciamento de dispositivos Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams na VDI com chat e colaboração

Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você pode definir políticas no nível do usuário para desativar a funcionalidade de chamada e reunião no Teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e reunião

Você pode definir políticas usando o Centro de administração do Microsoft Teams ou o PowerShell. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.

[**Políticas de chamada**](teams-calling-policy.md): o Teams inclui a política de chamada Interna DisallowCalling, na qual todos os recursos de chamada estão desligados. Atribua a política DisallowCalling a todos os usuários da sua organização que usam o Teams em um ambiente virtualizado.

[**Políticas de**](meeting-policies-in-teams.md)reunião : o Teams inclui a política de reunião AllOff interna, na qual todos os recursos de reunião estão desligados. Atribua a política AllOff a todos os usuários da sua organização que usam o Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Microsoft Teams

Para atribuir a política de chamada DisallowCalling e a política de reunião AllOff a um usuário:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1.  Em **Política de Chamada,** clique **em DisallowCalling**.
    2.  Em **Política de Reunião,** clique **em AllOff**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
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

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar o Teams na VDI com chat e colaboração para otimizar o Teams com chamada e reuniões

Se você tiver uma implementação existente do Teams no VDI com chat e colaboração na qual você definiu políticas no nível do usuário para desativar a funcionalidade de chamada e reunião e está migrando para o Teams com otimização de AV, você deve definir políticas para ativar a funcionalidade de chamada e reunião para esses Teams em usuários VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Definir políticas para ativar a funcionalidade de chamada e reunião

Você pode usar o Centro de administração do Microsoft Teams ou o PowerShell para definir e atribuir políticas de chamada e reunião aos usuários. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente após algumas horas.

[**Políticas de chamada:**](teams-calling-policy.md)as políticas de chamada no Teams controlam quais recursos de chamada estão disponíveis para os usuários. O Teams inclui a política interna de chamada AllowCalling, na qual todos os recursos de chamada estão ativas. Para ativar todos os recursos de chamada, atribua a política AllowCalling. Ou crie uma política de chamada personalizada para ativar os recursos de chamada que você deseja e atribuí-la aos usuários. 

[**Políticas de**](meeting-policies-in-teams.md)reunião : As políticas de reunião no Teams controlam os tipos de reuniões que os usuários podem criar e os recursos que estão disponíveis para os participantes da reunião agendados pelos usuários em sua organização. O Teams inclui a política de reunião AllOn interna, na qual todos os recursos de reunião estão ativas. Para ativar todos os recursos de reunião, atribua a política AllOn. Ou crie uma política de reunião personalizada para ativar os recursos de reunião que você deseja e atribuí-la aos usuários.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Microsoft Teams

Para atribuir a política de chamada AllowCalling e a política de reunião AllOn a um usuário:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários**.
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1.  Em **Política de Chamada,** clique **em AllowCalling**.
    2.  Em **Política de Reunião,** clique **em AllOn**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique na **&#x2713;** (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
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

## <a name="control-fallback-mode-in-teams"></a>Controlar o modo de fallback no Teams

Quando os usuários se conectam de um ponto de extremidade sem suporte, os usuários estão no modo de fallback, no qual a AV não é otimizada. Você pode desabilitar ou habilitar o modo de fallback definindo um dos seguintes valores DWORD do Registro:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Para desabilitar o modo de fallback, de definir o valor **como 1**. Para habilitar somente áudio, de definir o valor como **2**. Se o valor não estiver presente ou estiver definido como **0** (zero), o modo de fallback será habilitado.

Esse recurso está disponível no Teams versão 1.3.00.13565 e posterior.

## <a name="known-issues-and-limitations"></a>Problemas conhecidos e limitações

### <a name="client-deployment-installation-and-setup"></a>Implantação, instalação e instalação do cliente

- Com a instalação por máquina, o Teams na VDI não é atualizado automaticamente da maneira que os clientes do Teams não VDI são. Você precisa atualizar a imagem da VM instalando um novo MSI conforme descrito na seção Instalar ou atualizar o aplicativo de área de trabalho do [Teams na VDI.](#install-or-update-the-teams-desktop-app-on-vdi) Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- Em ambientes Citrix, se o usuário se desconectar da Máquina Virtual enquanto o Teams está em execução, as atualizações do Teams podem fazer com que o usuário esteja em um estado não otimizado para AV quando se reconectar. Recomendamos que os usuários saiam do Teams antes de se desconectar da Máquina Virtual citrix para evitar esse cenário.
- O Teams deve ser implantado por usuário ou por máquina. A implantação do Teams para simultâneo por usuário e por máquina não é suportada. Para migrar de cada máquina ou por usuário para um desses modos, siga o procedimento de desinstalação e reimplante para ambos os modos.
- A Área de Trabalho Virtual do Windows e a VMware não suportam clientes baseados em MacOS e Linux no momento.

### <a name="calling-and-meetings"></a>Chamada e reuniões

Os seguintes recursos de chamada e reunião não são suportados:

- Qualquer funcionalidade de várias janelas, como as novas experiências de reunião ou qualquer funcionalidade que venha com a nova experiência de reunião
- Serviços de emergência aprimorados
- Botões HID e controles DE LED entre o aplicativo e dispositivos do Teams
- Desfoque e efeitos em segundo plano
- Funções de apresentador e produtor de eventos ao vivo e transmissão
- Location-Based Roteamento (LBR)
- Estacionamento de chamada
- Fila de chamada
- Som de áudio/computador do sistema compartilhado
- Bypass de mídia para Roteamento Direto
- Controle zoom 

> [!NOTE]
> Estamos trabalhando na adição de recursos de chamada e reunião que estão disponíveis apenas em ambientes que não sejam VDI. Isso pode incluir mais controle de administrador sobre qualidade, cenários adicionais de compartilhamento de tela e recursos avançados adicionados recentemente ao Teams. Entre em contato com seu representante do Teams para saber mais sobre os recursos futuros.

A seguir estão os problemas conhecidos e limitações de chamada e reuniões:

- A interoperabilidade com o Skype for Business está limitada a chamadas de áudio; não há nenhuma modalidade de vídeo.
- Somente um único fluxo de vídeo de entrada é suportado em reuniões ou chamadas de grupo. Quando várias pessoas enviam vídeo, apenas o vídeo do alto-falante dominante é mostrado a qualquer momento.
- A resolução de fluxo de vídeo de entrada e saída é limitada à resolução de 720p. Essa é uma limitação do WebRTC.
- Há suporte para apenas um fluxo de vídeo de uma câmera de entrada ou de um fluxo de compartilhamento de tela. Quando há um compartilhamento de tela de entrada, esse compartilhamento de tela é mostrado, em vez do vídeo do alto-falante dominante.
- O Teams não alterna para usar o último dispositivo de áudio que um usuário selecionou, se o dispositivo estiver desconectado e, em seguida, reconectado.
- Compartilhamento de tela de saída:
    - Não há suporte para compartilhamento de aplicativos.
- Dê controle e controle:
    - Não há suporte durante uma sessão de compartilhamento de tela ou de aplicativo.
    - Suportado durante uma sessão de compartilhamento do PowerPoint.
- Limitações somente para Citrix
    - Quando o compartilhamento de tela em uma instalação com vários monitores, apenas o monitor principal é compartilhado.
    - Não há suporte para dimensionamento de DPI alto no CWA.

Para problemas conhecidos do Teams que não estão relacionados à VDI, consulte [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Solução de problemas

### <a name="troubleshoot-citrix-components"></a>Solucionar problemas de componentes do Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Falhas do Teams ou a tela de login do Teams está em branco

Esse é um problema conhecido com o Citrix VDA versões 1906 e 1909. Para resolver esse problema, adicione o seguinte valor DWORD do Registro e desmarca-o como 204 (hexadecimal).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Em seguida, reinicie o VDA. Para saber mais, confira este artigo de suporte do Citrix, Solução de problemas [de otimização HDX para o Teams.](https://support.citrix.com/article/CTX253754)

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Microsoft Teams usando MSI](msi-deployment.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar o Microsoft Teams na área de trabalho virtual do Windows](/azure/virtual-desktop/teams-on-wvd)
