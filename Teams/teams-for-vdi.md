---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Saiba como executar o Microsoft Teams em um ambiente VDI (Virtualized Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52c3a4fd1f8ce3871874468590662f223520dc07
ms.sourcegitcommit: 9787b84ab15ee2e14890151e966c81b4a4d43e62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868346"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para Infraestrutura de Área de Trabalho Virtualizada

Este artigo descreve os requisitos e limitações para usar o Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é VDI?

Virtual Desktop Infrastructure (VDI) é uma tecnologia de virtualização que hospeda um sistema operacional da área de trabalho e aplicativos em um servidor centralizado em um data center. Isso permite uma experiência de área de trabalho totalmente personalizada para usuários com uma fonte centralizada totalmente segura e compatível.

O Microsoft Teams em um ambiente virtualizado oferece suporte a chat e colaboração. E com as plataformas Windows Virtual Desktop, Citrix e VMware, a funcionalidade de chamada e reunião também é suportada.

O Teams em um ambiente virtualizado oferece suporte a várias configurações. Elas incluem modos VDI, dedicados, compartilhados, persistentes e não persistentes. Os recursos estão em desenvolvimento contínuo e são adicionados regularmente, e a funcionalidade se expandirá nos próximos meses e anos.

Usar o Teams em um ambiente virtualizado pode ser um pouco diferente de usar o Teams em um ambiente não virtualizado. Por exemplo, alguns recursos avançados podem não estar disponíveis em um ambiente virtualizado, e a resolução de vídeo pode ser diferente.

Para garantir uma experiência de usuário ideal, siga as orientações neste artigo.

> [!Note]
> Para obter detalhes sobre a VDI do Teams em diferentes plataformas, consulte [os recursos do Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams em componentes VDI

O uso do Teams em um ambiente virtualizado requer os seguintes componentes.

- **Agente de virtualização**: o gerenciador de recursos e conexões para o provedor de virtualização, como o Azure
- **Área de** trabalho virtual : a pilha de máquina virtual (VM) que executa o Microsoft Teams
- **Cliente fino**: o ponto de extremidade com o que o usuário faz interface física
- **Aplicativo da área de trabalho do Teams**: o aplicativo cliente da área de trabalho do Teams

## <a name="teams-on-vdi-requirements"></a>Teams em requisitos de VDI

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O aplicativo da área de trabalho do Teams foi validado com os principais provedores de soluções de virtualização. Com vários provedores de mercado, recomendamos que você consulte seu provedor de soluções de virtualização para garantir que você atender aos requisitos mínimos.
  
Atualmente, o Teams na VDI com otimização de áudio/vídeo (AV) é certificado com a Área de Trabalho Virtual do Windows, Citrix e VMware. Revise as informações nesta seção para garantir que você atender a todos os requisitos para a funcionalidade adequada.

### <a name="platforms-certified-for-teams"></a>Plataformas certificadas para o Teams

As plataformas a seguir têm soluções de infraestrutura de área de trabalho virtual para o Teams.

|Plataforma|Solução|
|----|---|
|![O logotipo que representa a Microsoft](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Área de Trabalho Virtual do Windows</a> |
|![O logotipo que representa Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![O logotipo que representa a VMware](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Área de Trabalho Virtual do Windows

A Área de Trabalho Virtual do Windows fornece otimização av para o Teams na VDI. Para saber mais e requisitos e instalação, [consulte Usar o Teams na Área de Trabalho Virtual do Windows.](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos do Citrix Virtual Apps and Desktops

O Citrix Virtual Apps and Desktops (anteriormente conhecido como XenApp e XenDesktop) fornece otimização AV para o Teams na VDI. Com o Citrix Virtual Apps and Desktops, o Teams na VDI oferece suporte à funcionalidade de chamada e reunião, além de chat e colaboração.

Você pode baixar a versão mais recente dos Aplicativos Virtuais e Áreas de Trabalho do [Citrix no site de downloads do Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Você precisará entrar primeiro.) Os componentes necessários são agrupados no [aplicativo Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) e no VDA (Virtual Delivery Agent) por padrão. Você não precisa instalar componentes adicionais ou plug-ins no CWA ou no VDA.

Para os requisitos mais recentes de servidor e cliente, consulte [este site da Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Requisitos de Área de Trabalho e Área de Trabalho do VMware Horizon

O VMware Horizon é uma plataforma moderna para entrega segura de áreas de trabalho virtuais e aplicativos em toda a nuvem híbrida. Para oferecer uma excelente experiência ao usuário final, o VMware Horizon fornece otimização de mídia para o Teams. Essa otimização melhora a produtividade geral em áreas de trabalho virtuais e aplicativos e melhora a experiência do usuário ao chamar e reunião usando o Teams.

Você pode baixar a versão mais recente do VMware Horizon na página [Downloads do VMware.](https://my.vmware.com/web/vmware/downloads/#all_products) Os componentes de otimização de mídia necessários fazem parte do Horizon Agent e do Cliente Horizon por padrão e não há necessidade de instalar qualquer plug-in adicional para usar o recurso de otimização do Teams.

Para obter os requisitos e instruções mais recentes sobre como configurar a otimização de mídia para o Teams, consulte [este site da VMware.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar ou atualizar o aplicativo da área de trabalho do Teams na VDI

Você pode implantar o aplicativo da área de trabalho do Teams para VDI usando uma instalação por máquina ou por usuário usando o pacote MSI. Decidir qual abordagem usar depende se você usa uma configuração persistente ou não persistente e as necessidades de funcionalidade associada da sua organização.

Para uma configuração persistente dedicada, qualquer abordagem funcionaria. No entanto, para uma configuração não persistente, o Teams requer uma instalação por máquina para funcionar com eficiência. Consulte a [seção de configuração não](#non-persistent-setup) persistente.

Com a instalação por computador, as atualizações automáticas são desabilitadas. Isso significa que, para atualizar o aplicativo Teams, você deve desinstalar a versão atual para atualizar para uma versão mais recente. Com a instalação por usuário, as atualizações automáticas são habilitadas. Para a maioria das implantações de VDI, recomendamos implantar o Teams usando a instalação por máquina.

Para atualizar para a versão mais recente do Teams, comece com o procedimento de desinstalação seguido pela implantação de versão mais recente do Teams.

Para que a otimização av do Teams em ambientes VDI funcione corretamente, o ponto de extremidade do cliente fino deve ter acesso à Internet. Se o acesso à Internet não estiver disponível no ponto de extremidade do cliente fino, a inicialização de otimização não será bem-sucedida. Isso significa que o usuário está em um estado de mídia não otimizado.

#### <a name="dedicated-persistent-setup"></a>Configuração persistente dedicada

Em uma configuração persistente dedicada, as alterações do sistema operacional local dos usuários são mantidas após o logoff dos usuários. Para configuração persistente, o Teams oferece suporte à instalação por usuário e por máquina.

A seguir está a configuração mínima de VM recomendada.

|Parâmetro  |Sistema operacional de estação de trabalho  |Sistema operacional do servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4,6 ou 8<br>É importante entender a configuração subjacente de acesso à memória não uniforme (NUMA) e configurar suas VMs de acordo.     |
|RAM     |   4 GB      | 512 a 1024 MB por usuário        |
|Armazenamento    | 8 GB        | 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuração não persistente

Em uma configuração não persistente, as alterações do sistema operacional local dos usuários não são mantidas após o logoff dos usuários. Essas configurações geralmente são sessões compartilhadas com vários usuários. A configuração da VM varia de acordo com o número de usuários e os recursos de caixa física disponíveis.

Para uma configuração não persistente, o aplicativo da área de trabalho do Teams deve ser instalado por máquina na imagem "ouro". (Para saber mais, consulte a seção Instalar ou atualizar o aplicativo da área de trabalho [do Teams na seção VDI.)](#install-or-update-the-teams-desktop-app-on-vdi) Isso garante uma iniciação eficiente do aplicativo Teams durante uma sessão do usuário.

O uso do Teams em uma configuração não persistente também requer um gerenciador de cache de perfil para uma sincronização eficiente de dados do tempo de execução do Teams. A sincronização eficiente de dados garante que as informações específicas do usuário apropriadas (como dados, perfil ou configurações do usuário) são armazenadas em cache durante a sessão do usuário. Certifique-se de que os dados dessas duas pastas sejam sincronizados:<br>
- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Uma pasta de roaming (ou, se você estiver usando o redirecionamento de pasta, um gerenciador de cache) é necessária para garantir que o aplicativo Teams tenha os dados e arquivos de tempo de execução necessários para executar o aplicativo. Isso é necessário para atenuar problemas de latência de rede ou falhas de rede, o que poderia causar erros de aplicativo e uma experiência lenta devido a dados e arquivos indisponíveis.

Há uma variedade de soluções de gerenciador de cache disponíveis. Por exemplo, [FSLogix](https://docs.microsoft.com/fslogix/overview). Consulte seu provedor de gerenciador de cache para obter instruções de configuração específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Lista de exclusão de conteúdo em cache do Teams para configuração não persistente

Exclua o seguinte da pasta de cache do Teams, %appdata%/Microsoft/Teams. Excluir esses itens ajuda a reduzir o tamanho do cache do usuário para otimizar ainda mais sua configuração não persistente.

- Arquivos .txt
- Pasta de pilha de mídia
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Considerações sobre o Microsoft 365 Apps para empresas

Considere o seguinte ao implantar o Teams com o Microsoft 365 Apps para empresas na VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Novas implantações do Teams por meio do Microsoft 365 Apps para empresas

Antes de implantar o Teams por meio do Microsoft 365 Apps para empresas, primeiro você deve desinstalar todos os aplicativos do Teams pré-existentes se eles foram implantados usando a instalação por computador.

O Teams por meio do Microsoft 365 Apps para empresas é instalado por usuário. Para saber mais, consulte a seção Instalar ou atualizar o aplicativo da área de trabalho [do Teams na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Implantações do Teams por meio do Microsoft 365 Apps para atualizações corporativas

O Teams também está sendo adicionado às instalações existentes do Microsoft 365 Apps para empresas. Como o Microsoft 365 Apps para empresas instala apenas o Teams por usuário, consulte a seção Instalar ou atualizar o aplicativo da área de trabalho [do Teams na seção VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Usando o Teams com a instalação por máquina e o Microsoft 365 Apps para empresas

O Microsoft 365 Apps para empresas não dá suporte a instalações por máquina do Teams. Para usar a instalação por máquina, você deve excluir o Teams do Microsoft 365 Apps para empresas. Consulte o aplicativo da área de trabalho Implantar o Teams na [VM](#deploy-the-teams-desktop-app-to-the-vm) e como excluir a implantação do Teams por meio de seções do [Microsoft 365 Apps para empresas.](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Como excluir a implantação do Teams por meio do Microsoft 365 Apps para empresas

Para saber mais sobre o Teams e o Microsoft 365 Apps para empresas, confira como excluir o Teams de novas instalações do [Microsoft 365 Apps para](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) empresas e usar a Política de Grupo para controlar a instalação do [Teams.](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implantar o aplicativo da área de trabalho do Teams na VM

1. Baixe o pacote MSI do Teams que corresponde ao sistema operacional VDI VM usando um dos seguintes links:

    - [Versão de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Versão de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Para nuvens governamentais, consulte Instalar o Microsoft Teams usando o [Microsoft Endpoint Configuration Manager](msi-deployment.md) para os links de download para os arquivos MSI.

    A versão mínima do aplicativo da área de trabalho do Teams necessária é a versão 1.3.00.4461. (A espera PSTN não é suportada em versões anteriores.)

2. Instale o MSI na VM VDI executando um dos seguintes comandos:

    - Instalação por usuário (padrão)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Esse processo é a instalação padrão, que instala o Teams na pasta de usuário %AppData%. Nesse ponto, a configuração da imagem dourada está concluída. O Teams não funcionará corretamente com a instalação por usuário em uma configuração não persistente.

    - Instalação por máquina

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Esse processo instala o Teams na pasta Arquivos de Programas (x86) em um sistema operacional de 64 bits e na pasta Arquivos de Programas em um sistema operacional de 32 bits. Nesse ponto, a configuração da imagem dourada está concluída. Instalar o Teams por computador é necessário para configurações não persistentes.

        A próxima sessão de logon interativo inicia o Teams e pede credenciais.

        > [!NOTE]
        > Esses exemplos também usam o **parâmetro ALLUSERS=1.** Quando você define este parâmetro, o Instalador de Todo o Computador do Teams aparece em Programas e recursos no Painel de Controle e em Aplicativos e Recursos nas Configurações do Windows para todos os usuários do computador. Todos os usuários podem desinstalar o Teams se eles têm credenciais de administrador.
        É importante entender a diferença entre **ALLUSERS=1** e **ALLUSER=1**. O **parâmetro ALLUSERS=1** pode ser usado em ambientes não VDI e VDI, enquanto o parâmetro **ALLUSER=1** é usado somente em ambientes VDI para especificar uma instalação por máquina.

3. Desinstale o MSI da VM VDI. Há duas maneiras de desinstalar o Teams.

    - Script do PowerShell: você pode usar [esse script do PowerShell](scripts/powershell-script-deployment-cleanup.md) para desinstalar o Teams e remover a pasta do Teams para um usuário. Execute o script para cada perfil de usuário no qual o Teams foi instalado no computador.
    - Linha de comando: Execute o seguinte comando.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Esse processo desinstala o Teams da pasta Arquivos de Programas (x86) ou da pasta Arquivos de Programas, dependendo do ambiente do sistema operacional.

## <a name="teams-on-vdi-performance-considerations"></a>Considerações de desempenho do Teams em VDI

Há uma variedade de configurações de configuração virtualizadas, cada uma com um foco diferente para otimização. Por exemplo, uma configuração pode se concentrar na densidade do usuário. Ao planejar, considere o seguinte para ajudar a otimizar a configuração com base nas necessidades de carga de trabalho da sua organização.

- Requisito mínimo: algumas cargas de trabalho podem exigir uma configuração usando recursos que estão acima dos requisitos mínimos. Por exemplo, cargas de trabalho para desenvolvedores que usam aplicativos que exigem mais recursos de computação.
- Dependências: incluem dependências de infraestrutura, carga de trabalho e outras considerações ambientais fora do aplicativo da área de trabalho do Teams.
- Recursos desabilitados na VDI: o Teams desabilita recursos intensivos de GPU para VDI, o que pode ajudar a melhorar a utilização transitória da CPU. Os seguintes recursos estão desabilitados:
    - Animação CSS do Teams
    - Início automático de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams na VDI com chamada e reuniões

Além de chat e colaboração, o Teams na VDI com chamada e reuniões está disponível com plataformas de provedores de virtualização com suporte. Os recursos com suporte são baseados na pilha de mídia WebRTC e na implementação do provedor de virtualização. O diagrama a seguir fornece uma visão geral da arquitetura.

![Diagrama mostrando o Teams na arquitetura VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Se você atualmente executar o Teams sem otimização de AV na VDI e usar recursos que ainda não são suportados para otimização (como Dar e controlar ao compartilhar aplicativos), será necessário definir políticas de provedor de virtualização para desativar o redirecionamento do Teams. Isso significa que as sessões de mídia do Teams não serão otimizadas. Para etapas sobre como definir políticas para desativar o redirecionamento do Teams, entre em contato com seu provedor de virtualização.

### <a name="network-requirements"></a>Requisitos de rede

Recomendamos que você avalie seu ambiente para identificar quaisquer riscos e requisitos que possam influenciar sua implantação geral de voz e vídeo na nuvem. Use a [Ferramenta de Avaliação de Rede](https://www.microsoft.com/download/details.aspx?id=53885) do Skype for Business para testar se sua rede está pronta para o Teams.

Para saber mais sobre como preparar sua rede para o Teams, confira [Preparar a rede da sua organização para o Teams.](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar do Skype for Business na VDI para o Teams na VDI

Se você estiver migrando do Skype for Business na VDI para o Teams na VDI, além das diferenças entre os dois aplicativos, haverá algumas diferenças quando a VDI também é implementada. Alguns recursos que atualmente não são suportados na VDI do Teams que estão no VDI do Skype for Business são os seguinte:

- Política por plataforma para desabilitar alguns recursos AV na VDI
- Dar e assumir o controle quando o compartilhamento de aplicativos
- Compartilhamento de tela do chat sem áudio
- Envio e recebimento simultâneo de vídeo e tela

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams no navegador Chrome versus aplicativo da área de trabalho do Teams para VDI

O navegador Teams no Chrome não fornece uma substituição para o aplicativo da área de trabalho do Teams para VDI com otimização av. A experiência de chat e colaboração funciona conforme o esperado. Quando a mídia é necessária, há algumas experiências que podem não atender às expectativas do usuário no navegador Chrome:

- A experiência de streaming de áudio e vídeo pode não ser ideal. Os usuários podem ter atrasos ou qualidade reduzida.
- As configurações do dispositivo não estão disponíveis nas configurações do navegador.
- O gerenciamento de dispositivos é manipulado pelo navegador e requer várias configurações nas configurações do site do navegador.
- As configurações do dispositivo também podem precisar ser definidas no gerenciamento de dispositivos Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams na VDI com chat e colaboração

Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você pode definir políticas de nível de usuário para desativar a funcionalidade de chamada e reunião no Teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e reunião

Você pode definir políticas usando o Centro de administração do Microsoft Teams ou o PowerShell. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.

[**Políticas de chamada:**](teams-calling-policy.md)o Teams inclui a política de chamada DisallowCalling interna, na qual todos os recursos de chamada estão desligados. Atribua a política DisallowCalling a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.

[**Políticas de**](meeting-policies-in-teams.md)reunião : o Teams inclui a política de reunião AllOff interna, na qual todos os recursos da reunião estão desligados. Atribua a política AllOff a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Microsoft Teams

Para atribuir a política de chamada DisallowCalling e a política de reunião AllOff a um usuário:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários.**
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

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **políticas de Chamada**  >  **de** Voz e clique em **DisallowCalling**.
    - Vá para **políticas de Reunião**  >  **de** Reuniões e clique **em AllOff**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada DisallowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamada, consulte [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOff a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrar o Teams na VDI com chat e colaboração para otimizar o Teams com chamada e reuniões

Se você tiver uma implementação existente do Teams na VDI com chat e colaboração em que definiu políticas de nível de usuário para desativar a funcionalidade de chamada e reunião e estiver migrando para o Teams com otimização de AV, deverá definir políticas para ativar a funcionalidade de chamada e reunião para esses usuários da VDI do Teams.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Definir políticas para ativar a funcionalidade de chamada e reunião

Você pode usar o Centro de administração do Microsoft Teams ou o PowerShell para definir e atribuir políticas de chamada e reunião aos seus usuários. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente após algumas horas.

[**Políticas de chamada:**](teams-calling-policy.md)as políticas de chamada no Teams controlam quais recursos de chamada estão disponíveis para os usuários. O Teams inclui a política de chamada Interna AllowCalling, na qual todos os recursos de chamada estão ativas. Para ativar todos os recursos de chamada, atribua a política AllowCalling. Ou crie uma política de chamada personalizada para ativar os recursos de chamada que você deseja e atribuí-la aos usuários. 

[**Políticas de**](meeting-policies-in-teams.md)reunião: as políticas de reunião no Teams controlam os tipos de reuniões que os usuários podem criar e os recursos que estão disponíveis para os participantes da reunião agendados pelos usuários em sua organização. O Teams inclui a política de reunião AllOn interna, na qual todos os recursos da reunião estão ativas. Para ativar todos os recursos de reunião, atribua a política AllOn. Ou crie uma política de reunião personalizada para ativar os recursos de reunião que você deseja e atribuí-la aos usuários.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Microsoft Teams

Para atribuir a política de chamada AllowCalling e a política de reunião AllOn a um usuário:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários.**
2. Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.
3. Siga este procedimento:
    1.  Em **Política de Chamada,** clique **em AllowCalling**.
    2.  Em **Política de Reunião,** clique **em AllOn**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, clique **no&#x2713;** (marca de seleção) na parte superior da tabela.
3. Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.

Ou você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **políticas de Chamada**  >  **de** Voz e clique **em AllowCalling**.
    - Vá para **políticas de Reunião**  >  **de** Reuniões e clique em **AllOn**.
2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada AllowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamada, consulte [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOn a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Controlar o modo de fallback no Teams

Quando os usuários se conectam de um ponto de extremidade sem suporte, os usuários estão no modo de fallback, no qual o AV não é otimizado. Você pode desabilitar ou habilitar o modo de fallback definindo um dos seguintes valores DWORD do Registro:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Para desabilitar o modo de fallback, de definir o valor como **1**. Para habilitar somente áudio, de definir o valor como **2**. Se o valor não estiver presente ou estiver definido como **0** (zero), o modo de fallback será habilitado.

Esse recurso está disponível no Teams versão 1.3.00.13565 e posterior.

## <a name="known-issues-and-limitations"></a>Problemas conhecidos e limitações

### <a name="client-deployment-installation-and-setup"></a>Implantação, instalação e configuração do cliente

- Com a instalação por máquina, o Teams na VDI não é atualizado automaticamente da maneira que os clientes do Teams não VDI são. Você precisa atualizar a imagem da VM instalando um novo MSI conforme descrito na seção Instalar ou atualizar o aplicativo da área de trabalho [do Teams na seção VDI.](#install-or-update-the-teams-desktop-app-on-vdi) Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- As equipes devem ser implantadas por usuário ou por máquina. Não há suporte para a implantação do Teams para usuários simultâneos e por máquina. Para migrar de cada máquina ou por usuário para um desses modos, siga o procedimento de desinstalação e reimplante para ambos os modos.
- A Área de Trabalho Virtual do Windows e a VMware não são suportadas por clientes baseados em MacOS e Linux no momento.
- O Citrix não dá suporte a clientes MacOs no momento.
- O Citrix não dá suporte ao uso de proxies HTTP explícitos definidos em um ponto de extremidade.

### <a name="calling-and-meetings"></a>Chamada e reuniões

Não há suporte para os seguintes recursos de chamada e reunião:

- Serviços de emergência aprimorados
- Botões HID e controles LED entre o aplicativo e os dispositivos do Teams
- Efeitos e desfoque de plano de fundo
- Funções de produtor e apresentador de eventos ao vivo e transmissão
- Location-Based roteamento (LBR)
- Estacionamento de chamada
- Fila de chamada
- Som de áudio/computador do sistema compartilhado
- Bypass de mídia para Roteamento Direto

> [!NOTE]
> Estamos trabalhando para adicionar recursos de chamada e reunião que estão atualmente disponíveis apenas em ambientes que não são VDI. Isso pode incluir mais controle de administrador sobre qualidade, cenários adicionais de compartilhamento de tela e recursos avançados adicionados recentemente ao Teams. Entre em contato com seu representante do Teams para saber mais sobre os recursos futuros.

A seguir estão problemas conhecidos e limitações para chamada e reuniões:

- A interoperabilidade com o Skype for Business está limitada a chamadas de áudio; não há modalidade de vídeo.
- Somente um único fluxo de vídeo de entrada é suportado em reuniões ou chamadas de grupo. Quando várias pessoas enviam vídeo, apenas o vídeo do alto-falante dominante é mostrado a qualquer momento.
- A resolução de fluxo de vídeo de entrada e saída está limitada à resolução de 720p. Esta é uma limitação de WebRTC.
- Apenas um fluxo de vídeo de uma câmera de entrada ou fluxo de compartilhamento de tela é suportado. Quando há um compartilhamento de tela de entrada, esse compartilhamento de tela é mostrado, em vez do vídeo do alto-falante dominante.
- O Teams não alterna para usar o último dispositivo de áudio que um usuário selecionou, se o dispositivo estiver desconectado e, em seguida, reconectado.
- Compartilhamento de tela de saída:
    - Não há suporte para compartilhamento de aplicativos.
- Dê controle e controle:
    - Não há suporte durante uma sessão de compartilhamento de tela ou de aplicativo.
    - Suportado durante uma sessão de compartilhamento do PowerPoint.
- Limitações somente citrix
    - Quando o compartilhamento de tela em uma instalação com vários monitores, somente o monitor principal é compartilhado.
    - Não há suporte para dimensionamento de DPI alto no CWA.

Para problemas conhecidos do Teams que não estão relacionados à VDI, consulte [Equipes de Suporte em sua organização.](Known-issues.md)

## <a name="troubleshooting"></a>Solução de problemas

### <a name="troubleshoot-citrix-components"></a>Solucionar problemas de componentes do Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Falhas do Teams ou a tela de login do Teams está em branco

Esse é um problema conhecido com o Citrix VDA versões 1906 e 1909. Para resolver esse problema, adicione o seguinte valor DWORD do Registro e de definida como 204 (hexadecimal).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Em seguida, reinicie o VDA. Para saber mais, confira este artigo de suporte do Citrix, [solucionando problemas de otimização hdx para o Teams.](https://support.citrix.com/article/CTX253754)

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Microsoft Teams usando MSI](msi-deployment.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar o Microsoft Teams na área de trabalho virtual do Windows](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
