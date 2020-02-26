---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Saiba como executar o Microsoft Teams em um ambiente de infraestrutura de área de trabalho virtualizada (VDI).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 479f272f45c4ac7c8f84f0aa26fe923ea16ff3d7
ms.sourcegitcommit: df552697ae9c8c01c40f816bbe98b251db147199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42278004"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams para Infraestrutura de Área de Trabalho Virtualizada

Este artigo descreve os requisitos e as limitações para usar o Microsoft Teams em um ambiente virtualizado.

## <a name="what-is-vdi"></a>O que é VDI?

A Virtual Desktop Infrastructure (VDI) é a tecnologia de virtualização que hospeda um sistema operacional e aplicativos de área de trabalho em um servidor centralizado em um Data Center. Isso permite uma experiência de área de trabalho totalmente personalizada para os usuários com uma fonte centralizada totalmente segura e compatível.
 
O Microsoft Teams em um ambiente virtualizado aceita chat e colaboração, e com a plataforma Citrix, a funcionalidade de chamada e reunião também tem suporte.

As equipes em um ambiente virtualizado dão suporte a várias configurações. Isso inclui modos de VDI, dedicado, compartilhado, persistente e não persistente. Os recursos estão em desenvolvimento contínuo e são adicionados regularmente, e a funcionalidade será ampliada nos próximos meses e anos.
 
Usar o Microsoft Teams em um ambiente virtualizado pode ser um pouco diferente de usar o Microsoft Teams em um ambiente não virtualizado. Por exemplo, alguns recursos avançados podem não estar disponíveis em um ambiente virtualizado e a resolução de vídeo pode ser diferente. Para garantir uma experiência de usuário ideal, siga as orientações deste artigo.

## <a name="teams-on-vdi-components"></a>Teams on VDI Components

Usar o Microsoft Teams em um ambiente virtualizado requer os componentes a seguir.

- **Agente de virtualização**: o Gerenciador de recursos e conexão com o provedor de virtualização, como o Azure
- **Área de trabalho virtual**: pilha da máquina virtual (VM) que executa o Microsoft Teams
- **Cliente leve**: o ponto de extremidade com o qual o usuário se interfaces fisicamente
- **Aplicativo da área de trabalho Teams**: é o aplicativo cliente da área de trabalho do teams

## <a name="teams-on-vdi-requirements"></a>Teams on VDI requirements

### <a name="virtualization-provider-requirements"></a>Requisitos do provedor de virtualização

O aplicativo da área de trabalho Teams foi validado com provedores de soluções de virtualização líderes. Com vários provedores de mercado, recomendamos que você consulte seu provedor de soluções de virtualização para garantir que os requisitos mínimos sejam atendidos.
  
Atualmente, o Teams on VDI com otimização de áudio/vídeo (AV) é certificado pela Citrix. Revise as informações nesta seção para garantir que os requisitos do Citrix e do teams sejam atendidos de acordo com a funcionalidade adequada.

### <a name="partners-certified-for-teams"></a>Parceiros certificados para equipes

Os parceiros a seguir têm soluções de infraestrutura de área de trabalho virtual para Teams.

|Sócio|Solução de parceiros|
|----|---|
|![O logotipo que representa a Citrix](media/citrix.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Aplicativos e áreas de trabalho virtuais do Citrix</a> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Requisitos para aplicativos e áreas de trabalho do Citrix virtual

Aplicativos e áreas de trabalho virtuais do Citrix (anteriormente conhecido como XenApp e XenDesktop) fornecem otimização de AV para Teams no VDI. Com os aplicativos e áreas de trabalho virtuais do Citrix, o Teams no VDI é compatível com a funcionalidade de chamada e reunião, além de chat e colaboração.

Você pode baixar a versão mais recente dos aplicativos e áreas de trabalho virtuais da Citrix [aqui](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Você precisará entrar primeiro.) Os componentes necessários são incluídos no aplicativo de [espaço de trabalho do Citrix (CWA)](https://www.citrix.com/downloads/workspace-app/) e no agente de entrega virtual (VDA) por padrão. Você não precisa instalar outros componentes ou plug-ins adicionais no CWA ou no VDA.

Para obter os requisitos mais recentes do servidor e do cliente, consulte [este website da Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Instalar ou atualizar o aplicativo da área de trabalho Teams no VDI

Você pode implantar o aplicativo da área de trabalho Teams para VDI usando uma instalação por computador ou instalação por usuário usando o pacote MSI. Decidir qual abordagem usar depende se você usa uma configuração persistente ou não persistente e as necessidades de funcionalidade associadas à sua organização.
Para uma configuração persistente dedicada, qualquer uma das abordagens funcionaria.  No entanto, para uma configuração não persistente, a instalação por máquina é necessária para que as equipes trabalhem com eficiência. Consulte a seção [configuração não persistente](#non-persistent-setup) .

Com a instalação por máquina, as atualizações automáticas estão desabilitadas. Isso significa que para atualizar o aplicativo Teams, você deve desinstalar a versão atual para atualizar para uma versão mais recente. Com a instalação por usuário, as atualizações automáticas são habilitadas. Para a maioria das implantações de VDI, recomendamos implantar o Microsoft Teams usando a instalação por máquina.

Para atualizar para a versão mais recente do Teams, comece com o procedimento de desinstalação seguido pela implantação da versão mais recente do teams.

Para que a otimização de AV do Team em ambientes de VDI funcione corretamente, o ponto de extremidade do cliente leve deve ter acesso à Internet. Se o acesso à Internet não estiver disponível no ponto de extremidade do cliente fino, a inicialização da otimização não será bem-sucedida. Isso significa que o usuário está em um estado de mídia não otimizado.

#### <a name="dedicated-persistent-setup"></a>Configuração persistente dedicada

Em uma configuração persistente dedicada, as alterações do sistema operacional local dos usuários são mantidas após o logoff dos usuários.  Para configuração persistente, o Teams é compatível com a instalação por usuário e por computador.

A seguir está a configuração mínima de VM recomendada.

|Parâmetro  |Sistema operacional de estação de trabalho  |Sistema operacional do servidor  |
|---------|---------|---------|
|vCPU   |    2 núcleos     |  4, 6 ou 8<br>É importante entender a configuração de NUMA (acesso não uniforme à memória) subjacente e configurar suas VMs de acordo.     |
|RAM     |   4 GB      | de 512 a 1024 MB por usuário        |
|Armazenamento    | 8 GB        | de 40 a 60 GB        |

#### <a name="non-persistent-setup"></a>Configuração não persistente

Em uma configuração não persistente, as alterações do sistema operacional local dos usuários não são mantidas após o logoff dos usuários. Essas configurações geralmente são sessões de vários usuários compartilhadas. A configuração da VM varia de acordo com o número de usuários e os recursos de caixa física disponíveis.

Para uma configuração não persistente, o aplicativo da área de trabalho Teams deve ser instalado por computador para a imagem dourada. (Para saber mais, confira a seção [instalar ou atualizar o aplicativo Teams desktop no VDI](#install-or-update-the-teams-desktop-app-on-vdi) ). Isso garante uma inicialização eficiente do aplicativo Teams durante uma sessão de usuário. Usar o Microsoft Teams com uma configuração não persistente também exige um Gerenciador de cache de perfis para sincronização eficiente de dados do teams Runtime. Isso garante que as informações apropriadas específicas do usuário (por exemplo, dados do usuário, perfil e configurações) sejam armazenadas em cache durante a sessão do usuário.  Há diversas soluções do caching Manager disponíveis. Por exemplo, [FSLogix](https://docs.microsoft.com/fslogix/overview). Consulte o provedor do Gerenciador de armazenamento em cache para obter instruções de configuração específicas.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Lista de exclusão de conteúdo em cache da Teams para configuração não persistente

Exclua o seguinte da pasta de armazenamento do Teams,% AppData%/Microsoft/Teams.  Excluir esses ajuda a reduzir o tamanho do cache do usuário para otimizar ainda mais a configuração que não está persistente.

- arquivos. txt
- Mídia-pasta de pilha

### <a name="office-365-proplus-considerations"></a>Considerações sobre o Office 365 ProPlus

Considere o seguinte ao implantar o Microsoft Teams com o Office 365 ProPlus em VDI.

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a>Novas implantações de Teams por meio do Office 365 ProPlus

Antes de implantar o Microsoft Teams por meio do Office 365 ProPlus, você deve primeiro desinstalar todos os aplicativos do teams que foram implantados usando a instalação por máquina.

As equipes por meio do Office 365 ProPlus são instaladas por usuário. Para saber mais, confira a seção [instalar ou atualizar o aplicativo Teams desktop no VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-office-365-proplus-updates"></a>Implantações de equipes por meio do Office 365 ProPlus atualizações

As equipes também estão sendo adicionadas às instalações existentes do Office 365 ProPlus. Como o Office 365 ProPlus instala o Microsoft Teams por usuário somente, consulte a seção [instalar ou atualizar o aplicativo Teams desktop no VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a>Usar o Microsoft Teams com a instalação por computador e o Office 365 ProPlus

O Office 365 ProPlus não é compatível com instalações por máquina do teams. Para usar a instalação por máquina, você deve excluir equipes do Office 365 ProPlus. Consulte o [aplicativo implantar o Teams desktop na VM](#deploy-the-teams-desktop-app-to-the-vm) e [como excluir a implantação de equipes por meio das seções do Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) .

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a>Como excluir a implantação do Microsoft Teams por meio do Office 365 ProPlus

Para saber mais sobre o Teams e o Office 365 ProPlus, consulte [como excluir equipes de novas instalações do office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) e [usar a política de grupo para controlar a instalação do teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Implantar o aplicativo da área de trabalho Teams na VM

1. Baixe o pacote MSI do teams que corresponde ao seu sistema operacional VDI VM usando um dos seguintes links:

    - [Versão de 32 bits](https://statics.teams.cdn.office.net/production-windows/1.2.00.32462/Teams_windows.msi)
    - [Versão de 64 bits](https://statics.teams.cdn.office.net/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    A versão mínima do aplicativo de área de trabalho Teams necessário é a versão 1.2.00.31357. (A suspensão PSTN não é suportada em versões anteriores).

2. Instale o MSI na VM do VDI executando um dos seguintes comandos:

    - Instalação por usuário (padrão)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        Esta é a instalação padrão, que instala o Microsoft Teams na pasta de usuários% AppData%. Nesse ponto, a configuração da imagem dourada está concluída. O Microsoft Teams não funcionará corretamente com a instalação por usuário em uma configuração não persistente.
    
    - Instalação por máquina

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        Isso instala o Microsoft Teams na pasta arquivos de programas (x86) em um sistema operacional de 64 bits e na pasta arquivos de programas em um sistema operacional de 32 bits. Nesse ponto, a configuração da imagem dourada está concluída. A instalação do teams por computador é necessária para configurações não persistentes.
 
        A próxima sessão de logon interativo inicia o Teams e pede credenciais.

3. Desinstale o MSI da VM VDI. 

    Há duas maneiras de desinstalar o Microsoft Teams:  
  
    - Script do PowerShell (recomendado)
    
    - Linha de comando: essa abordagem remove equipes, ainda que a reinstalação do teams seja renovada. Execute o seguinte comando:
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      Isso desinstala o Teams da pasta arquivos de programas (x86) ou da pasta arquivos de programas, dependendo do ambiente do sistema operacional.

## <a name="teams-on-vdi-performance-considerations"></a>Teams sobre considerações de desempenho do VDI

Há diversas configurações de configuração virtualizadas, cada uma com um foco diferente para otimização. Por exemplo, densidade do usuário. Ao planejar, considere o seguinte para ajudar a otimizar sua configuração com base nas necessidades de carga de trabalho da sua organização:

- Necessidade mínima: algumas cargas de trabalho podem exigir uma configuração que esteja acima dos requisitos mínimos. Por exemplo, cargas de trabalho para desenvolvedores que usam aplicativos que exigem mais recursos de computação.
- Dependências: isso inclui dependências de infraestrutura, carga de trabalho e outras considerações ambientais fora do aplicativo da área de trabalho Teams.
- Recursos desabilitados no VDI: o Teams desabilita recursos de uso intensivo da GPU para VDI, o que pode ajudar a melhorar a utilização transitória da CPU. Os recursos a seguir estão desativados:
    - Animação CSS do teams
    - Início automático do Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams on VDI com chamadas e reuniões

Além de chat e colaboração, o Microsoft Teams no VDI com suporte a chamadas e reuniões está disponível com plataformas baseadas em Citrix. Os recursos com suporte se baseiam na pilha de mídia do WebRTC e na implementação específica da Citrix. O diagrama a seguir fornece uma visão geral da arquitetura.

![Diagrama mostrando o Microsoft Teams na arquitetura VDI](media/teams-on-vdi-architecture.png)

Não há suporte para estes recursos de chamada e reunião:

- Serviços de emergência aprimorados
- Botões e controles de LED HID entre o aplicativo e os dispositivos do teams
- Desfoque e efeitos em segundo plano
- Transmissão/eventos ao vivo
- Roteamento baseado em local (LBR)
- Estacionamento de chamada
- Fila de chamadas

> [!IMPORTANT]
> Se você atualmente executa o Teams sem otimização de AV na VDI e usa recursos que ainda não têm suporte para otimização (como conceder e assumir o controle quando o compartilhamento de aplicativos), você precisa definir políticas Citrix para desativar o redirecionamento de equipe. Isso significa que as sessões de mídia do Teams não serão otimizadas. Para ver as etapas sobre como definir políticas para desativar o redirecionamento de equipes, consulte este [website da Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).

Estamos nos empenhando para adicionar recursos de chamada e reunião que atualmente só estão disponíveis em ambientes não VDI. Isso pode incluir mais controle de administração sobre qualidade, cenários adicionais de compartilhamento de tela e recursos avançados recentemente adicionados ao Teams. Entre em contato com o representante da equipe para saber mais sobre os recursos futuros.

### <a name="network-requirements"></a>Requisitos de rede

Recomendamos que você avalie seu ambiente para identificar quaisquer riscos e requisitos que possam influenciar a sua distribuição geral de voz e vídeo em nuvem. Use a [ferramenta de avaliação de rede do Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) para testar se sua rede está pronta para o Teams.

Para saber mais sobre como preparar sua rede para o Microsoft Teams, consulte [preparar a rede da sua organização para equipes](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrar do Skype for Business no VDI para o Microsoft Teams no VDI

Se você estiver migrando do Skype for Business no VDI para o Teams no VDI, além das diferenças entre os dois aplicativos, há algumas diferenças quando o VDI também é implementado. Alguns recursos que atualmente não são compatíveis com o VDI do teams na VDI do Skype for Business são os seguintes:

- Controle de experiências de chamada VDI com políticas para limitar a taxa de bits de mídia
- Política por plataforma para desabilitar alguns recursos AV do VDI
- Conceder e assumir o controle quando o compartilhamento de aplicativos
- Compartilhamento de tela de chat sem áudio
- Envio e recebimento simultâneos de vídeo e de tela

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams no navegador Chrome versus aplicativo da área de trabalho do teams para VDI

O Microsoft Teams no navegador Chrome não permite a substituição do aplicativo Teams desktop para VDI com otimização AV. A experiência de chat e colaboração funciona como esperado. Quando a mídia é necessária, há algumas experiências que talvez não atendam às expectativas dos usuários no navegador Chrome:

- A experiência de áudio e streaming de vídeo pode não ser ideal. Os usuários podem enfrentar atrasos ou qualidade reduzida.
- As configurações do dispositivo não estão disponíveis nas configurações do navegador.
- O gerenciamento de dispositivos é administrado pelo navegador e requer várias configurações nas configurações do site do navegador.
- As configurações do dispositivo também devem ser definidas no gerenciamento de dispositivos do Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams on VDI com chat e colaboração

Se a sua organização quiser usar somente os recursos de chat e colaboração do Teams, você poderá definir políticas em nível de usuário para desativar a funcionalidade de chamada e reunião no Microsoft Teams. Este nível de recurso não requer áreas de trabalho e aplicativos virtuais da Citrix.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e de reunião

Você pode definir políticas usando o centro de administração do Microsoft Teams ou o PowerShell. Pode levar algum tempo (algumas horas) para que as alterações de política sejam propagadas. Se você não vir as alterações de uma determinada conta imediatamente, tente novamente em algumas horas.

Como fazer [**chamadas para políticas**](teams-calling-policy.md): o Teams inclui a política interna de chamada DisallowCalling, na qual todos os recursos de chamada são desativados. Atribua a política DisallowCalling a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.

[**Políticas de reunião**](meeting-policies-in-teams.md): o Teams inclui a política de reunião interna do AllOff, na qual todos os recursos da reunião estão desativados. Atribua a política AllOff a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Microsoft Teams

Para atribuir a política de chamada do DisallowCalling e a política de reunião do AllOff aos usuários, siga estas etapas:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**.
2. Selecione o usuário clicando à esquerda do nome do usuário e, em seguida, clique em **Editar configurações**.
3. Do the following:
    1.  Em **política de chamada**, clique em **DisallowCalling**.
    2.  Em **política de reunião**, clique em **AllOff**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários de uma vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).

Ou, você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **** > **políticas de chamadas**de voz e clique em **DisallowCalling**.
    - Vá para **** > **políticas de reunião**de reuniões e clique em **AllOff**.
3. Escolha **Gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, clique em **salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar o [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada DisallowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

Para saber mais sobre como usar o PowerShell para gerenciar as políticas de chamadas, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar o [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião do AllOff a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

Para saber mais sobre como usar o PowerShell para gerenciar as políticas de reunião, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a>Migrar o Microsoft Teams no VDI com chat e colaboração para o Citrix com chamadas e reuniões

Se você tiver uma implementação existente do teams no VDI com chat e colaboração em que você definiu políticas em nível de usuário para desativar a funcionalidade de chamada e reunião e estiver migrando para o Citrix com a otimização do AV, você deve definir políticas para ativar a chamada e funcionalidade de reunião para essas equipes em usuários da VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Definir políticas para ativar a funcionalidade de chamada e de reunião

Você pode usar o centro de administração do Microsoft Teams ou o PowerShell para definir e atribuir políticas de chamada e reunião para seus usuários. Pode levar algum tempo (algumas horas) para que as alterações de política sejam propagadas. Se você não vir as alterações de uma determinada conta imediatamente, tente novamente em algumas horas.

Como fazer [**chamadas**](teams-calling-policy.md)para políticas: as políticas de chamada no Teams controlam quais recursos de chamada estão disponíveis para os usuários. O Teams inclui a política de chamada AllowCalling interna, na qual todos os recursos de chamada estão ativados. Para ativar todos os recursos de chamada, atribua a política AllowCalling. Ou crie uma política de chamada personalizada para ativar os recursos de chamada desejados e atribuí-la aos usuários. 

[**Políticas de reunião**](meeting-policies-in-teams.md): as políticas de reunião no Teams controlam os tipos de reuniões que os usuários podem criar e os recursos que estão disponíveis para os participantes de reuniões agendados pelos usuários da sua organização. O Teams inclui a política de reunião habilitada interna, na qual todos os recursos da reunião estão ativados. Para ativar todos os recursos da reunião, atribua a política do recurso. Ou crie uma política de reunião personalizada para ativar os recursos de reunião desejados e atribuir usuários a ele.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Microsoft Teams

Para atribuir a política de chamada do AllowCalling e a política de reunião do usuário para os usuários, siga estas etapas:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**.
2. Selecione o usuário clicando à esquerda do nome do usuário e, em seguida, clique em **Editar configurações**.
3. Do the following:
    1.  Em **política de chamada**, clique em **AllowCalling**.
    2.  Em **política de reunião**, clique em **permitir**.
4. Clique em **Aplicar**.

Para atribuir uma política a vários usuários de uma vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).

Ou, você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:
    - Vá para **** > **políticas de chamadas**de voz e clique em **AllowCalling**.
    - Vá para **** > **políticas de reunião**de reuniões e clique em **permitir**.
3. Escolha **Gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, clique em **salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar o [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada AllowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

Para saber mais sobre como usar o PowerShell para gerenciar as políticas de chamadas, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar o [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião de permissão a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

Para saber mais sobre como usar o PowerShell para gerenciar as políticas de reunião, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

### <a name="client-deployment-installation-and-setup"></a>Implantação, instalação e configuração do cliente

- Com a instalação por máquina, o Teams não é atualizado automaticamente na maneira como os clientes de equipes não VDI. Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção [instalar ou atualizar o aplicativo da área de trabalho do teams no VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
- O Teams deve ser implantado por usuário ou por computador. Não há suporte para a implantação de equipes simultâneas por usuário e por computador.  Para migrar de cada computador ou por usuário para um desses modos, siga o procedimento de desinstalação e reimplante para qualquer um dos modos.
- No momento, os clientes baseados em Linux e MacOs não são compatíveis com o Citrix.
- A Citrix não oferece suporte ao uso de proxies HTTP explícitos definidos em um ponto de extremidade. 

### <a name="calling-and-meetings"></a>Chamadas e reuniões

- A interoperabilidade com o Skype for Business está limitada a chamadas de áudio, sem modalidade de vídeo.
- Não há suporte para a interação DTMF (Dual Tone Multi Frequency) com sistemas de telefonia no momento.
- Ingressar em reuniões do Microsoft Teams como um usuário anônimo não é otimizado para AV. O usuário pode participar da reunião e ter uma experiência não otimizada.
- Só há suporte para um único fluxo de vídeo de entrada em reuniões ou chamadas em grupo. Quando várias pessoas enviam vídeo, somente o vídeo da palestrante dominante é mostrado a qualquer momento.  
- A resolução de fluxo de vídeo de entrada e saída está limitada à resolução de 720p. Esta é uma limitação WebRTC.
- Só há suporte para um fluxo de vídeo de uma câmera de entrada ou de um fluxo de compartilhamento de tela. Quando há um compartilhamento de tela recebido, esse compartilhamento de tela é mostrado em vez do vídeo do alto-falante dominante.
- Compartilhamento de tela de saída:
    - Não há suporte para compartilhamento de aplicativos.
- Conceda controle e assuma o controle:  
    - Sem suporte durante uma sessão de compartilhamento de tela ou compartilhamento de aplicativos.
    - Com suporte durante uma sessão de compartilhamento do PowerPoint.  
- Não há suporte para o dimensionamento de DPI alta em CWA.

Para os problemas conhecidos do teams que não estão relacionados ao VDI, consulte [problemas conhecidos do teams](Known-issues.md).

## <a name="troubleshooting"></a>Solução de problemas

#### <a name="troubleshoot-citrix-components"></a>Solução de problemas para componentes da Citrix

Para obter informações sobre como solucionar problemas de VDA e CWA, consulte [este website da Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Microsoft Teams usando MSI](msi-deployment.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
