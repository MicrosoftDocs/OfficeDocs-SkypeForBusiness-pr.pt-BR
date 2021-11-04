---
title: Novidades no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Resumo: leia este tópico para saber mais sobre novos recursos no Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte Lync agora Skype for Business -- confira novidades.'
ms.openlocfilehash: aac68c369983b85ecb95b5000dc41d95e2080d6d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760559"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novidades no Skype for Business Server 2015

**Resumo:** Leia este tópico para saber mais sobre novos recursos no Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Lync agora Skype for Business -- consulte novidades](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
O Lync agora Skype for Business, uma plataforma de comunicação e colaboração que reúne uma experiência inspirada pelo Skype com a segurança, a conformidade e o controle de nível empresarial do Lync. Skype for Business oferece recursos, incluindo presença, mensagens de IM, chamadas de voz e vídeo e reuniões online. Skype for Business fornece uma nova experiência de cliente, uma nova versão do servidor e atualizações para o serviço em Microsoft 365 ou Office 365. Se os usuários em sua organização já estão familiarizados com o Skype, eles apreciarão o poder e a simplicidade do Skype for Business onde é fácil encontrar e se conectar com colegas de trabalho. Se os usuários em sua organização estão vindo para Skype for Business do Lync, eles reconhecerão todos os recursos que já usam, mas em uma nova interface nova com controles simplificados e novas adições. Além da nova experiência do cliente, o Skype for Business Server 2015 fornece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais e soluções híbridas.
  
Novos recursos no Skype for Business Server 2015 incluem melhorias para:
  
- Experiência do usuário  
- Suporte a voz e vídeo
- Suporte móvel
- Gerenciamento de servidores locais
- Implantação e gerenciamento de soluções híbridas
- Suporte à autenticação multifa factor
    
## <a name="user-experience"></a>Experiência do usuário

O Skype for Business cliente é muito semelhante à versão de consumidor do Skype e usa os mesmos botões e ícones. Menos menus e uma hierarquia de tarefas simples facilitam para os usuários encontrar rapidamente os controles e comandos necessários. 
  
Skype for Business inclui a nova experiência do usuário descrita acima e a experiência do usuário do Lync 2013 lançada anteriormente. A inclusão de ambas as experiências permite que as empresas gerenciem as alterações para seus usuários controlando o processo e o tempo da nova versão do cliente. A experiência do usuário padrão depende de qual versão do servidor você está usando. Os administradores escolhem a experiência preferencial usando o cmdlet **Set-CsClientPolicy** com o parâmetro EnableSkypeUI. Para obter mais informações sobre como configurar a experiência do cliente, consulte [Configure the client experience with Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) and Desktop client feature comparison for [Skype for Business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> A experiência do cliente do Lync 2013 não é uma opção para Skype for Business versões do cliente 2016. Antes de tentar configurar seu ambiente cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não comece com o número 16; por exemplo: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Melhorias de voz e vídeo

Skype for Business Server 2015 inclui melhorias na funcionalidade de voz e vídeo, incluindo coleta e análise de dados de chamadas e interoperabilidade aprimorada com sistemas de teleconferência de vídeo de terceiros.
  
### <a name="call-data-collection-and-analysis"></a>Análise e coleta de dados de chamada

O recurso Rate My Call permite que Skype for Business Server administradores de 2015 coletem dados de chamada. Esse recurso está disponível apenas para implantações locais. Os usuários são solicitados a fazer uma pesquisa após a conclusão de uma chamada. Para obter mais informações, [consulte Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilidade aprimorada com sistemas de teleconferência de vídeo de terceiros

O VIS (Video Interop Server) atua como um intermediário entre os sistemas Skype for Business Server e VTC (Video Teleconferencing) da Cisco. Ao ingressar em uma reunião, os usuários agora podem selecionar um sistema VTC cisco. O VIS (Servidor de Interop de Vídeo) é implementado como uma função de servidor autônomo para implantações locais. Para obter mais informações, [consulte Plan for Video Interop Server in Skype for Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Chamada via Trabalho

O recurso Chamada por Trabalho permite que os usuários corporativos façam chamadas de voz do cliente Skype for Business. Quando um usuário faz uma chamada de voz, ela é roteada de Skype for Business para o telefone PBX ou PSTN do originador. Depois que o originador atender o telefone, a chamada será direcionada para o número de destino. O destinatário da chamada responde e a chamada é estabelecida com Skype for Business servindo como o painel de controle. O originador pode gerenciar seus controles de presença e chamada Skype for Business. Os administradores de servidor habilitam e configuram a Chamada via Trabalho para a empresa. Para obter mais informações, [consulte Plan for Call Via Work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Melhorias no suporte a dispositivos móveis

As melhorias no suporte a dispositivos móveis incluem recursos para melhorar a experiência móvel para usuários Edição Enterprise, como acesso ao histórico de conversas e dados de log, experiências aprimoradas de reunião móvel e suporte a logoff único em Office. Além disso, há melhorias no suporte ao Android, melhorias de desempenho e recursos para simplificar a integração por meio da Estrutura de Aplicativos Comuns. 
  
> [!NOTE]
> Os servidores UCWA do Lync 2013 devem ser atualizados para o Skype for Business Server 2015 para dar suporte a clientes móveis. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>O histórico de conversas do lado do servidor agora está disponível em dispositivos móveis

Para habilitar o acesso móvel ao histórico de conversas, iMs perdidas e dados de log de chamada, o arquivamento dessas informações agora é processado por meio do servidor para todos os clientes móveis. O recurso de aceitação automática para mensagens IM melhora a confiabilidade, impedindo mensagens de tempo de tempo de uso do servidor quando um usuário móvel não responde a um IM imediatamente. Para aproveitar a integração de pastas Exchange/Outlook baseadas em servidor, Exchange Server 2013 ou clientes móveis mais novos e atualizados são necessários. 
  
### <a name="enhanced-meeting-experiences"></a>Experiências de reunião aprimoradas

A funcionalidade de reunião disponível na área de trabalho agora também está disponível para usuários móveis. A nova funcionalidade inclui:
  
- Navegação assíncrona de conteúdo PowerPoint compartilhado
- Capacidade do apresentador de assumir o controle do conteúdo PowerPoint compartilhado
- Gerenciamento de lobby para apresentadores, permitindo que eles admitam ou neguem participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business melhorias no Android

Skype for Business no Android agora oferece recursos semelhantes ao que está disponível no Skype for Business no iOS e Skype for Business no Windows:
  
- Continuar ou ingressar em conversas
- Habilitar autenticação passiva e certificado
- Convidar outras pessoas para uma conversa
- Iniciar conversas de grupo facilmente
- Participar de uma reunião sem ser um Skype for Business usuário
- Habilitar a interface do usuário do smartphone em tablets Android
- Gerenciar reuniões adicionando ou removendo participantes
    
> [!NOTE]
> Esses recursos exigem o sistema operacional Android versão 4.0 ou superior. 
  
## <a name="management-of-on-premises-servers"></a>Gerenciamento de servidores locais

O Skype for Business Server 2015 fornece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais, incluindo a atualização local, a instalação inteligente, os processos de correção e atualização aprimorados, recursos aprimorados de início a frio do pool de front-end, suporte SQL Server AlwaysOn e log centralizado e solução de problemas.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Atualização in-local para servidores locais

Agora você pode atualizar os sistemas do Lync Server 2013 para o Skype for Business Server 2015 usando o novo recurso de atualização local, que usa investimentos existentes de hardware e servidor do Lync Server 2013, reduzindo assim o custo geral para implantar o Skype for Business Server 2015.
  
Há dois cenários para atualização in-locar: o método Move User, que não requer tempo de inatividade, e o método Offline, que exige tempo de inatividade. Para obter mais informações sobre qual procedimento de atualização é o correto para sua empresa, consulte [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> A opção in-locar não estará disponível se você estiver atualizando do Lync Server 2010. Para obter mais informações sobre a atualização do Lync Server 2010, consulte [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Instalação Inteligente

O recurso de Instalação Inteligente, que detecta e baixa automaticamente as atualizações, agora faz parte do programa de Instalação. Durante o processo de instalação, o usuário é perguntado se o processo de instalação deve verificar se há atualizações. Para obter mais informações, [consulte Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Processo de atualização e correção aprimorado do Servidor front-end

Skype for Business Server apresenta dois novos cmdlets que ajudam a tornar a atualização ou a correção de Servidores Front-End muito mais fácil do que nas versões anteriores do Lync Server.
  
Quando você precisar aplicar um patch ou executar qualquer outra manutenção, a um Servidor Front-End, basta digitar **Invoke-CsComputerFailOver** e especificar o nome desse servidor. Skype for Business Server a carga de trabalho desse servidor temporariamente para os outros servidores no pool. Em seguida, você pode executar a manutenção e, em seguida, usar o cmdlet **Invoke-CsComputerFailback** para trazer esse servidor de volta ao serviço. Se você precisar corrigir cada servidor em um pool, basta seguir este procedimento para cada servidor, um de cada vez. Esses novos cmdlets permitem corrigir servidores muito mais rápidos do que nas versões anteriores e com mais confiabilidade e um fluxo de trabalho mais simples.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Funcionalidade de início a frio do pool front-end aprimorado

Skype for Business Server apresenta um novo cmdlet que simplifica e melhora o processo de iniciar a frio todo um pool de Front-End. Quando você usa o novo cmdlet **Start-CsPool,** ele verifica os pré-requisitos de todos os Servidores Front-End no pool e tenta iniciar cada servidor. Se encontrar algum problema, ele os diagnosticará e o alertará com detalhes e soluções alternativas. Em alguns casos, ele permite que você inicie o pool mesmo que alguns dos servidores individuais não sejam capazes de iniciar.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server Suporte AlwaysOn para servidores locais

Skype for Business Server 2015 adiciona suporte SQL Server Grupos de Disponibilidade AlwaysOn e SQL Server Instâncias de Cluster de Failover AlwaysOn. Além desses recursos, o Skype for Business Server continua o suporte para espelhamento de banco de dados e SQL Server clustering, como nas versões anteriores do Lync Server.
  
SQL Server Grupos de Disponibilidade AlwaysOn é uma solução de alta disponibilidade e recuperação de desastres no SQL Server 2012 e SQL Server 2014 que fornece uma alternativa ao espelhamento de banco de dados. Um grupo de disponibilidade oferece suporte a um ambiente de failover para um conjunto discreto de bancos de dados (conhecidos como bancos de dados de disponibilidade) que falham juntos. Um grupo de disponibilidade oferece suporte a um conjunto de bancos de dados primários de leitura e gravação e um a quatro conjuntos de bancos de dados secundários correspondentes. Opcionalmente, bancos de dados secundários podem ser disponibilizados para acesso somente leitura e para algumas operações de backup.
  
SQL Server As Instâncias de Cluster de Failover aproveitam Windows funcionalidade WSFC (Clustering de Failover do Servidor) para fornecer alta disponibilidade local por meio de redundância no nível da instância do servidor — uma instância de cluster de failover (FCI). Um FCI é uma única instância de SQL Server que é instalada nos nós do WSFC (Cluster de Failover do Servidor) do Windows e, possivelmente, em várias sub-redes.
  
Para obter mais informações, [consulte Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Melhorias centralizadas de registro em log e solução de problemas para servidores locais

O Serviço de Log Centralizado é o ambiente de registro em log preferencial para Skype for Business Server 2015. Não há novos recursos nesta versão, mas a confiabilidade e o desempenho foram aprimorados para o serviço e o Agente de Serviço de Log Centralizado (ClsAgent.exe)-- o executável de serviço que se comunica com o controlador e recebe comandos emitidos pelo administrador.
  
Skype for Business Server 2015 usa Windows PowerShell cmdlets para gerenciar os agentes de serviço de registro em log, iniciar o rastreamento e gerar relatórios. (O Lync Server 2013 ClsController.exe para executar essas tarefas.)
  
O Serviço de Log Centralizado pode ser executado em qualquer Skype for Business Server 2015. Os cenários integrados (rastreamentos pré-definidos) permanecem os mesmos, assim como a capacidade de criar cenários personalizados. Há um cenário especial chamado AlwaysOn que está sempre em execução e permite que os administradores localizem problemas comuns em quase tempo real.
  
A ferramenta de depuração snooper também foi atualizada para permitir a depuração de logs de mobilidade e funcionará com dispositivos que se conectam ao Lync 2013 ou Skype for Business Server 2015. A ferramenta está disponível como um download da Web das ferramentas [de Depuração.](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>Implantação híbrida e gerenciamento

Skype for Business Server 2015 habilita recursos de gerenciamento e administração de implantação híbrida introduzindo os seguintes recursos:
  
- Recomendações para implantações híbridas com base no estado dos ativos locais do cliente, conforme determinado pela ferramenta de assistência Office 365 OnRamp.
- Aprimoramentos no Painel de Controle Skype for Business Server e no Centro de Administração Skype for Business Server para que os administradores possam usar essas ferramentas para gerenciar uma implantação híbrida.
- Aprimoramentos do Painel de Controle que permitem que os administradores entre em um locatário Microsoft 365 ou Office 365 e configurar o híbrido com o Skype for Business Online usando o assistente de configuração híbrida.
- Suporte ao Painel de Controle para mover usuários locais para Skype for Business Online ou Skype for Business usuários Online de volta para o local.
- Recursos do Painel de Controle para identificar e filtrar objetos de usuário locais que foram movidos para o Skype for Business Online (ou seja, usuários híbridos) de usuários locais.
- Recursos do Centro de Administração para identificar e filtrar usuários de nuvem criados inicialmente no Skype for Business Online de usuários híbridos migrados do local para o Online.
- A capacidade de administrar usuários híbridos usando o Painel de Controle para propriedades gerenciáveis no local e o Centro de Administração para propriedades gerenciáveis Skype for Business Online.
- Usando a Sincronização de Senhas com DirSync, a capacidade de sincronizar senhas locais do Active Directory com o locatário online. Se configurado, esse recurso removerá a necessidade de implantar o AD FS para autenticação federada, mas o AD FS ainda é necessário para autenticação multifato. 
- Suporte contínuo para coexistência entre Skype for Business Online e Exchange local.
    
> [!NOTE]
> Não há nenhuma alteração do Lync Online 2013 e Exchange experiência de suporte local. 
  
## <a name="multi-factor-authentication"></a>Autenticação multifator

A autenticação multifato é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada de segurança crítica às insuções e transações do usuário. Por exemplo, exigindo um nome de usuário e senha e um certificado. Skype for Business Server 2015 continua a se basear nos recursos de autenticação multifato disponíveis nas Atualizações Cumulativas do Lync Server 2013. As alterações significativas na autenticação multifa factor são:
  
- Uso da biblioteca de autenticação do Active Directory Office 2013 SP1 para integração com Exchange e SharePoint
- Suporte para o recurso de autenticação multifação no Skype for Business Web App cliente
    
Com Skype for Business autenticação multifaionária, agora é possível fornecer diferentes opções de autenticação com base na geografia. Por exemplo, os clientes podem configurar seu ambiente para que a autenticação interna se basee na Autenticação integrada Windows, enquanto os funcionários que são autenticados de fora da organização usam autenticação multifa factor. 
  
A Skype for Business de autenticação multifato é perfeita, independentemente de:
  
- Localização Geográfica - Se o usuário está se insando de dentro ou fora da organização 
- Tipo de cliente/dispositivo - qual Skype for Business cliente é usado e qual dispositivo o cliente está executando (computador, celular, iPad, etc.)
- Local da conta - Se o usuário está hospedado em um Active Directory local ou em Azure Active Directory Online.
