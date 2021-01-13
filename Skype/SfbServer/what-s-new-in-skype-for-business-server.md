---
title: Novidades no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Resumo: Leia este tópico para saber mais sobre os novos recursos do Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte Lync agora é o Skype for Business. Veja as novidades.'
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827581"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novidades no Skype for Business Server 2015

**Resumo:** Leia este tópico para saber mais sobre os novos recursos do Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Lync agora](https://go.microsoft.com/fwlink/p/?LinkId=529022)é o Skype for Business – veja as novidades.
  
O Lync agora é o Skype for Business, uma plataforma de comunicação e colaboração que reúne uma experiência inspirado no Skype com a segurança, conformidade e controle de nível empresarial do Lync. O Skype for Business oferece recursos, incluindo presença, IM, chamadas de voz e vídeo e reuniões online. O Skype for Business oferece uma nova experiência de cliente, uma nova versão de servidor e atualizações para o serviço no Microsoft 365 ou Office 365. Se os usuários em sua organização já estão familiarizados com o Skype, eles vão gostar do poder e da simplicidade do Skype for Business onde é fácil encontrar e se conectar com colegas de trabalho. Se os usuários em sua organização estão vindo para o Skype for Business a partir do Lync, eles reconhecerão todos os recursos que já usam, mas em uma nova interface com controles simplificados e novas adições. Além da nova experiência do cliente, o Skype for Business Server 2015 fornece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais e soluções híbridas.
  
Novos recursos no Skype for Business Server 2015 incluem melhorias para:
  
- Experiência do usuário  
- Suporte a voz e vídeo
- Suporte móvel
- Gerenciamento de servidores locais
- Implantação e gerenciamento de soluções híbridas
- Suporte à autenticação multifa factor
    
## <a name="user-experience"></a>Experiência do usuário

O cliente Skype for Business é muito semelhante à versão para consumidores do Skype e usa os mesmos botões e ícones. Menos menus e uma hierarquia de tarefas mais plana facilitam para os usuários encontrar rapidamente os controles e comandos de que precisam. 
  
O Skype for Business inclui a nova experiência do usuário descrita acima e a experiência de usuário do Lync 2013 lançada anteriormente. A inclusão de ambas as experiências permite que as empresas gerenciem mudanças para seus usuários controlando o processo e o tempo da nova lançamento do cliente. A experiência padrão do usuário depende de qual versão do servidor você está usando. Os administradores escolhem a experiência preferida usando o cmdlet **Set-CsClientPolicy** com o parâmetro EnableSkypeUI. Para obter mais informações sobre como configurar a experiência do cliente, consulte Configurar a experiência do cliente com a comparação de recursos do cliente [Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) e Desktop para o Skype for [Business.](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> A experiência de cliente do Lync 2013 não é uma opção para versões de cliente do Skype for Business 2016. Antes de tentar configurar seu ambiente cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ela não comece com o número 16; por exemplo: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Melhorias de voz e vídeo

O Skype for Business Server 2015 inclui melhorias na funcionalidade de voz e vídeo, incluindo coleta e análise de dados de chamadas e interoperabilidade aprimorada com sistemas de teleconferência de vídeo de terceiros.
  
### <a name="call-data-collection-and-analysis"></a>Análise e coleta de dados de chamada

O recurso Rate My Call permite que os administradores do Skype for Business Server 2015 coletem dados de chamadas. Esse recurso está disponível somente para implantações locais. Os usuários são solicitados a fazer uma pesquisa depois de concluir uma chamada. Para obter mais informações, [consulte Rate my Call in Skype for Business Server 2015.](manage/health-and-monitoring/rate-my-call.md)
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Melhor interoperabilidade com sistemas de teleconferência de vídeo de terceiros

O Servidor de Interop de Vídeo (VIS) atua como um intermediário entre o Skype for Business Server e os sistemas de teleconferência de vídeo (VTC) da Cisco. Ao ingressar em uma reunião, os usuários agora podem selecionar um sistema VTC da Cisco. O Servidor de Interop de Vídeo (VIS) é implementado como uma função de servidor autônoma para implantações locais. Para obter mais informações, [consulte Plan for Video Interop Server in Skype for Business Server 2015.](plan-your-deployment/video-interop-server.md)
  
### <a name="call-via-work"></a>Telefonar via Trabalho

O recurso Telefonar via Trabalho permite que usuários corporativos façam chamadas de voz do cliente Skype for Business. Quando um usuário faz uma chamada de voz, ela é roteada do Skype for Business para o telefone PBX ou PSTN do originador. Depois que o originador atender o telefone, a chamada será então direcionada para o número de destino. O destinatário da chamada atende e a chamada é estabelecida com o Skype for Business servindo como o painel de controle. O originador pode gerenciar seus controles de presença e chamada do Skype for Business. Os administradores de servidor habilitam e configuram a Chamada via Trabalho para a empresa. Para obter mais informações, [consulte Plan for Call Via Work in Skype for Business Server 2015.](plan-your-deployment/enterprise-voice-solution/call-via-work.md) 
  
## <a name="mobile-device-support-improvements"></a>Melhorias no suporte a dispositivos móveis

As melhorias no suporte a dispositivos móveis incluem recursos para melhorar a experiência móvel dos usuários do Enterprise Edition, como acesso ao histórico de conversas e dados de log, experiências aprimoradas de reuniões móveis e suporte a logoff único no Office. Além disso, há melhorias no suporte ao Android, melhorias de desempenho e recursos para simplificar a integração por meio da Estrutura de Aplicativos Comuns. 
  
> [!NOTE]
> Os servidores UCWA do Lync 2013 devem ser atualizados para o Skype for Business Server 2015 para dar suporte a clientes móveis. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>O histórico de conversas no servidor agora está disponível em dispositivos móveis

Para habilitar o acesso móvel ao histórico de conversas, IM perdida e dados de log de chamada, o arquivamento dessas informações agora é processado por meio do servidor para todos os clientes móveis. O recurso de aceitação automática para mensagens automáticas melhora a confiabilidade, impedindo o tempo de vida das mensagens de servidor quando um usuário móvel não responde a uma IM imediatamente. Para aproveitar a integração de pastas do Exchange/Outlook baseadas em servidor, o Exchange Server 2013 ou mais novo e os clientes móveis atualizados são necessários. 
  
### <a name="enhanced-meeting-experiences"></a>Experiências de reunião aprimoradas

A funcionalidade de reunião disponível na área de trabalho agora também está disponível para usuários móveis. A nova funcionalidade inclui:
  
- Navegação assíncrona de conteúdo compartilhado do PowerPoint
- Capacidade do apresentador de assumir o controle do conteúdo compartilhado do PowerPoint
- Gerenciamento de lobby para apresentadores, permitindo que eles admitir ou negar participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Melhorias do Skype for Business no Android

O Skype for Business no Android agora oferece recursos semelhantes aos disponíveis no Skype for Business no iOS e no Skype for Business no Windows:
  
- Continuar ou ingressar em conversas
- Habilitar a autenticação de certificado e passiva
- Convidar outras pessoas para uma conversa
- Iniciar conversas em grupo facilmente
- Ingressar em uma reunião sem ser um usuário do Skype for Business
- Habilitar a interface do usuário do smartphone em tablets Android
- Gerenciar reuniões adicionando ou removendo participantes
    
> [!NOTE]
> Esses recursos exigem o sistema operacional Android versão 4.0 ou superior. 
  
## <a name="management-of-on-premises-servers"></a>Gerenciamento de servidores locais

O Skype for Business Server 2015 oferece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais, incluindo atualização local, instalação inteligente, processos aprimorados de patch e atualização, melhor capacidade de início a frio do pool de #A0, suporte ao SQL Server AlwaysOn e solução de problemas e registro centralizado.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Atualização local para servidores locais

Agora você pode atualizar os sistemas do Lync Server 2013 para o Skype for Business Server 2015 usando o novo recurso de atualização in-locar, que usa investimentos existentes em hardware e servidor do Lync Server 2013, reduzindo assim o custo geral para implantar o Skype for Business Server 2015.
  
Há dois cenários para a atualização in-locar: o método Mover Usuário, que não requer tempo de inatividade, e o método Offline, que exige tempo de inatividade. Para obter mais informações sobre qual procedimento de atualização é o correto para sua empresa, consulte Planejar a atualização para o [Skype for Business Server 2015.](plan-your-deployment/upgrade.md) 
  
> [!NOTE]
> A opção local não estará disponível se você estiver atualizando do Lync Server 2010. Para obter mais informações sobre como atualizar do Lync Server 2010, consulte Plano para atualizar para [o Skype for Business Server 2015.](plan-your-deployment/upgrade.md) 
  
### <a name="smart-setup"></a>Smart Setup

O recurso Smart Setup, que detecta e baixa automaticamente atualizações, agora faz parte do programa de Instalação. Durante o processo de instalação, o usuário é perguntado se o processo de instalação deve verificar se há atualizações. Para obter mais informações, [consulte Instalar o Skype for Business Server 2015.](deploy/install/install.md)
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Processo aprimorado de a correção e atualização do Servidor Front End

O Skype for Business Server apresenta dois novos cmdlets que ajudam a tornar a atualização ou a correção dos Servidores Front End muito mais fácil do que nas versões anteriores do Lync Server.
  
Quando precisar aplicar um patch ou realizar qualquer outra manutenção em um Servidor Front-End, basta digitar **Invoke-CsComputerFailOver** e especificar o nome desse servidor. O Skype for Business Server move temporariamente a carga de trabalho desse servidor para os outros servidores no pool. Em seguida, você pode realizar a manutenção e usar o cmdlet **Invoke-CsComputerFailback** para colocar esse servidor de volta em serviço. Se você precisar corrigir cada servidor em um pool, basta seguir este procedimento para cada servidor, um de cada vez. Esses novos cmdlets permitem corrigir servidores muito mais rápido do que em versões anteriores e com mais confiabilidade e um fluxo de trabalho mais simples.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Capacidade aprimorada de início a frio do pool de Front End

O Skype for Business Server apresenta um novo cmdlet que simplifica e aprimora o processo de início a frio de um pool de Front-End inteiro. Quando você usa o novo cmdlet **Start-CsPool,** ele verifica os pré-requisitos de todos os Servidores front-end no pool e tenta iniciar cada servidor. Se encontrar algum problema, ele os diagnosticará e alertará você com detalhes e soluções alternativas. Em alguns casos, ele permite que você inicie o pool mesmo que alguns servidores individuais não sejam capazes de iniciar.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Suporte alwaysOn do SQL Server para servidores locais

O Skype for Business Server 2015 adiciona suporte para Grupos de Disponibilidade AlwaysOn do SQL Server e Instâncias de Cluster de Failover alwaysOn do SQL Server. Além desses recursos, o Skype for Business Server continua a dar suporte ao espelhamento de banco de dados e clustering do SQL Server, como nas versões anteriores do Lync Server.
  
Os Grupos de Disponibilidade AlwaysOn do SQL Server são uma solução de recuperação de desastres e alta disponibilidade no SQL Server 2012 e no SQL Server 2014 que fornece uma alternativa ao espelhamento de banco de dados. Um grupo de disponibilidade oferece suporte a um ambiente de failover para um conjunto discreto de bancos de dados (conhecidos como bancos de dados de disponibilidade) que são failover juntos. Um grupo de disponibilidade suporta um conjunto de bancos de dados primários de leitura e gravação e um a quatro conjuntos de bancos de dados secundários correspondentes. Opcionalmente, bancos de dados secundários podem ser disponibilizados para acesso somente leitura e para algumas operações de backup.
  
As Instâncias de Cluster de Failover do SQL Server aproveitam a funcionalidade do WSFC (Clustering de Failover do Windows Server) para fornecer alta disponibilidade local por meio de redundância no nível da instância do servidor — uma instância de cluster de failover (FCI). Uma FCI é uma única instância do SQL Server instalada nos nós do WSFC (Clustering de Failover do Windows Server) e, possivelmente, em várias sub-redes.
  
Para obter mais informações, [consulte Plan for high availability and disaster recovery in Skype for Business Server 2015.](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Melhorias de registro centralizado em log e solução de problemas para servidores locais

O Serviço de Log Centralizado é o ambiente de registro em log preferido para o Skype for Business Server 2015. Não há novos recursos nesta versão, mas a confiabilidade e o desempenho foram aprimorados para o serviço e o Agente de Serviço de Log Centralizado (ClsAgent.exe) – o executável de serviço que se comunica com o controlador e recebe comandos emitidos pelo administrador.
  
O Skype for Business Server 2015 usa cmdlets do Windows PowerShell para gerenciar os agentes de serviço de registro em log, iniciar o rastreamento e gerar relatórios. (O Lync Server 2013 ClsController.exe para executar essas tarefas.)
  
O Serviço de Log Centralizado pode ser executado em qualquer Skype for Business Server 2015. Os cenários integrados (rastreamentos pré-definidos) permanecem os mesmos, assim como a capacidade de criar cenários personalizados. Há um cenário especial chamado AlwaysOn que está sempre em execução e permite que os administradores localizem problemas comuns quase em tempo real.
  
A ferramenta de depuração Snooper também foi atualizada para permitir a depuração de logs de mobilidade e funcionará com dispositivos que se conectam ao Lync 2013 ou ao Skype for Business Server 2015. A ferramenta está disponível como um download da Web das ferramentas [de depuração.](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>Implantação e gerenciamento híbridos

O Skype for Business Server 2015 permite recursos de gerenciamento e administração de implantação híbrida, apresentando os seguintes recursos:
  
- Recomendações para implantações híbridas com base no estado dos ativos locais do cliente, conforme determinado pela ferramenta de assistência automatizada OnRamp para Office 365.
- Aprimoramentos no Painel de Controle do Skype for Business Server e no Centro de Administração do Skype for Business Server para que os administradores possam usar essas ferramentas para gerenciar uma implantação híbrida.
- Aprimoramentos do Painel de Controle que permitem aos administradores entrar em um locatário do Microsoft 365 ou Office 365 e configurar o híbrido com o Skype for Business Online usando o assistente de configuração híbrida.
- Suporte ao Painel de Controle para mover usuários locais para o Skype for Business Online ou mover os usuários do Skype for Business Online de volta para o local.
- Recursos do Painel de Controle para identificar e filtrar objetos de usuário locais que foram movidos para o Skype for Business Online (ou seja, usuários híbridos) de usuários locais.
- Recursos do Centro de Administração para identificar e filtrar usuários na nuvem criados inicialmente no Skype for Business Online de usuários híbridos migrados do local para o Online.
- A capacidade de administrar usuários híbridos usando o Painel de Controle para propriedades gerenciáveis no local e o Centro de Administração para propriedades gerenciáveis do Skype for Business Online.
- Usando a Sincronização de Senha com o DirSync, a capacidade de sincronizar senhas do Active Directory local com o locatário online. Se configurado, esse recurso elimina a necessidade de implantar o AD FS para autenticação federada, mas o AD FS ainda é necessário para a autenticação multifato. 
- Suporte contínuo para coexistência entre o Skype for Business Online e o Exchange local.
    
> [!NOTE]
> Não há nenhuma alteração da experiência de suporte e coexistência do Lync Online 2013 e do Exchange local. 
  
## <a name="multi-factor-authentication"></a>Autenticação multifator

A autenticação multifato é um método de autenticação que exige o uso de mais de um método de verificação e adiciona uma segunda camada crítica de segurança a transações e logins do usuário. Por exemplo, exigir um nome de usuário e senha e um certificado. O Skype for Business Server 2015 continua a se basear nos recursos de autenticação multifação disponíveis nas Atualizações Cumulativas do Lync Server 2013. As alterações significativas na autenticação multifa factor são:
  
- Uso da Biblioteca de Autenticação do Active Directory do Office 2013 SP1 para integração com o Exchange e o SharePoint
- Suporte para o recurso de autenticação multifa factor no cliente do Skype for Business Web App
    
Com a autenticação multifatare do Skype for Business, agora é possível fornecer opções de autenticação diferentes com base em geografia. Por exemplo, os clientes podem configurar seu ambiente para que a autenticação interna depende da Autenticação Integrada do Windows, enquanto os funcionários que fazem a autenticação de fora da organização usam a autenticação multifatório. 
  
A experiência de autenticação multifatofa do Skype for Business é perfeita, independentemente de:
  
- Localização Geográfica - Se o usuário está se inndo de dentro ou de fora da organização 
- Tipo de cliente/dispositivo - qual cliente do Skype for Business é usado e em qual dispositivo o cliente está sendo executado (computador, celular, iPad, etc.)
- Local da Conta - Se o usuário está hospedado em um Active Directory local ou no Azure Active Directory Online.
