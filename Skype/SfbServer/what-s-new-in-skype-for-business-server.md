---
title: O que há de novo no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: Leia este tópico para saber mais sobre os novos recursos no Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte Lync agora é Skype for Business – Veja o que há de novo.'
ms.openlocfilehash: b8d0d8334977b5367419991d1bcabba303718c89
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221081"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>O que há de novo no Skype for Business Server 2015

**Resumo:** Leia este tópico para saber mais sobre os novos recursos no Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Lync agora é Skype for Business – Veja o que há de novo](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
O Lync agora é o Skype for Business, uma plataforma de comunicação e colaboração que reúne uma experiência inspirado pelo Skype com a segurança, a conformidade e o controle de nível empresarial do Lync. O Skype for Business oferece recursos, incluindo presença, mensagens instantâneas, chamadas de voz e vídeo e reuniões online. O Skype for Business fornece uma nova experiência de cliente, uma nova versão do servidor e atualizações para o serviço no Microsoft 365 ou no Office 365. Se os usuários da sua organização já estiverem familiarizados com o Skype, eles apreciarão a potência e a simplicidade do Skype for Business onde é fácil encontrar e se conectar com colegas de trabalho. Se os usuários da sua organização estiverem chegando ao Skype for Business do Lync, reconhecerão todos os recursos que eles já usam, mas em uma nova interface com controles simplificados e novas adições. Além da nova experiência do cliente, o Skype for Business Server 2015 fornece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais e soluções híbridas.
  
Os novos recursos do Skype for Business Server 2015 incluem melhorias em:
  
- Experiência do usuário  
- Suporte para voz e vídeo
- Suporte móvel
- Gerenciamento de servidores locais
- Implantação e gerenciamento de soluções híbridas
- Suporte à autenticação multifator
    
## <a name="user-experience"></a>Experiência do usuário

O cliente Skype for Business é muito semelhante à versão de consumidor do Skype e usa os mesmos botões e ícones. Menos menus e uma hierarquia de tarefas do Flatter facilitam a localização rápida dos controles e dos comandos necessários. 
  
O Skype for Business inclui a nova experiência do usuário descrita acima e a experiência do usuário do Lync 2013 lançada anteriormente. A inclusão de ambas as experiências permite que as empresas gerenciem alterações para seus usuários, controlando o processo e o período da nova distribuição do cliente. A experiência do usuário padrão depende de qual versão do servidor você está usando. Os administradores escolhem a experiência preferencial usando o cmdlet **set-CsClientPolicy** com o parâmetro EnableSkypeUI. Para obter mais informações sobre como configurar a experiência do cliente, consulte [Configure the Client Experience with Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) and [Desktop Client Feature Comparison for Skype for Business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> A experiência de cliente do Lync 2013 não é uma opção para as versões do cliente do Skype for Business 2016. Antes de tentar configurar seu ambiente de cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não inicie com o número 16; por exemplo: 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Aprimoramentos de vídeo e voz

O Skype for Business Server 2015 inclui melhorias na funcionalidade de voz e vídeo, incluindo a coleta e a análise de dados de chamadas e a interoperabilidade aprimorada com sistemas de teleconferência de vídeo de terceiros.
  
### <a name="call-data-collection-and-analysis"></a>Coleta e análise de dados de chamada

O recurso Rate My Call permite que os administradores do Skype for Business Server 2015 coletem dados de chamada. Este recurso está disponível apenas para implantações locais. Os usuários são solicitados a fazer uma pesquisa após concluir uma chamada. Para obter mais informações, consulte [Rate My call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Melhor interoperabilidade com sistemas de teleconferência de vídeo de terceiros

O servidor de interoperabilidade de vídeo (VIS) atua como intermediário entre o Skype for Business Server e os sistemas VTC (teleconferência de vídeo Cisco). Ao ingressar em uma reunião, os usuários agora podem selecionar um sistema Cisco VTC. O servidor de interoperabilidade de vídeo (VIS) é implementado como uma função de servidor autônomo para implantações locais. Para obter mais informações, consulte [Plan for video Interop Server in Skype for Business server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Ligar via trabalho

O recurso call via Work permite que os usuários corporativos façam chamadas de voz do cliente Skype for Business. Quando um usuário faz uma chamada de voz, ele é roteado do Skype for Business para o PBX ou telefone PSTN do originador. Depois que o originador responder ao telefone, a chamada será direcionada para o número de destino. O destinatário da chamada responde e a chamada é estabelecida com o Skype for Business servindo como o painel de controle. O originador pode gerenciar seus controles de presença e de chamada do Skype for Business. Os administradores de servidor habilitam e configuram chamadas via trabalho para a empresa. Para obter mais informações, consulte [Plan for Call via work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Aprimoramentos de suporte a dispositivos móveis

Aprimoramentos no suporte a dispositivos móveis incluem recursos para melhorar a experiência móvel para usuários do Enterprise Edition, como acesso a histórico de conversas e dados de log, experiências avançadas de reunião móvel e suporte a logon único no Office. Além disso, há melhorias no suporte ao Android, melhorias de desempenho e recursos para simplificar a integração por meio da estrutura de aplicativos comum. 
  
> [!NOTE]
> Os servidores do Lync 2013 UCWA devem ser atualizados para o Skype for Business Server 2015 para dar suporte a clientes móveis. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>O histórico da conversa do servidor está agora disponível em dispositivos móveis

Para habilitar o acesso móvel a histórico de conversas, mensagens instantâneas perdidas e dados de log de chamadas, o arquivamento dessas informações agora é processado através do servidor para todos os clientes móveis. O recurso de aceitação automática para IM aumenta a confiabilidade, impedindo mensagens de tempo limite do servidor quando um usuário móvel não responde a uma mensagem instantânea imediatamente. Para aproveitar as vantagens da integração de pastas do Exchange/Outlook baseadas em servidor, o Exchange Server 2013 ou mais recente e clientes móveis atualizados são necessários. 
  
### <a name="enhanced-meeting-experiences"></a>Experiências de reunião aprimoradas

A funcionalidade de reunião disponível na área de trabalho agora também está disponível para usuários móveis. A nova funcionalidade inclui:
  
- Navegação assíncrona de conteúdo compartilhado do PowerPoint
- A capacidade do apresentador de assumir o controle do conteúdo compartilhado do PowerPoint
- Gerenciamento de lobby para apresentadores, permitindo que eles contenham ou neguem participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business em aprimoramentos do Android

O Skype for Business no Android agora oferece recursos semelhantes ao que está disponível no Skype for Business no iOS e no Skype for Business no Windows:
  
- Continuar ou associar novamente as conversas
- Habilitar certificado e autenticação passiva
- Convidar outras pessoas para uma conversa
- Iniciar as conversas de grupo facilmente
- Participar de uma reunião sem ser um usuário do Skype for Business
- Habilitar a interface do usuário do smartphone em tablets Android
- Gerenciar reuniões adicionando ou removendo participantes
    
> [!NOTE]
> Esses recursos exigem o Android OS versão 4,0 ou superior. 
  
## <a name="management-of-on-premises-servers"></a>Gerenciamento de servidores locais

O Skype for Business Server 2015 oferece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais, incluindo a atualização in-loco, a instalação inteligente, os processos aprimorados de correção e atualização, o recurso de início Cold de pool de front-end, o suporte a SQL Server AlwaysOn e o registro em log e a solução de problemas centralizados.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Atualização in-loco para servidores locais

Agora você pode atualizar os sistemas do Lync Server 2013 para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco, que usa o Lync Server 2013 de hardware e o servidor existentes do Lync Server, reduzindo assim o custo geral para implantar o Skype for Business Server 2015.
  
Há dois cenários para a atualização in-loco: o método move User, que não requer nenhum tempo de inatividade e o método offline, que requer tempo de inatividade. Para obter mais informações sobre qual procedimento de atualização é ideal para sua empresa, consulte [plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> A opção in-loco não estará disponível se você estiver atualizando do Lync Server 2010. Para obter mais informações sobre a atualização do Lync Server 2010, consulte [plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configuração inteligente

O recurso de instalação inteligente, que detecta e baixa automaticamente as atualizações, agora faz parte do programa de instalação. Durante o processo de instalação, o usuário será perguntado se o processo de instalação deve verificar se há atualizações. Para obter mais informações, consulte [instalar o Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Patch de servidor front-end aprimorado e processo de atualização

O Skype for Business Server apresenta dois novos cmdlets que ajudam a tornar a atualização ou o patch de servidores front-end muito mais fácil do que nas versões anteriores do Lync Server.
  
Quando precisar aplicar um patch ou executar qualquer outra manutenção, em um servidor front-end, basta digitar **Invoke-CsComputerFailOver** e especificar o nome do servidor. O Skype for Business Server move a carga de trabalho desse servidor temporariamente para os outros servidores do pool. Você pode executar a manutenção e, em seguida, usar o cmdlet **Invoke-CsComputerFailback** para trazer o servidor de volta para o serviço. Se você precisar corrigir cada servidor em um pool, basta seguir este procedimento para cada servidor, um de cada vez. Esses novos cmdlets permitem que você corrija servidores muito mais rápido do que nas versões anteriores e com mais confiabilidade e um fluxo de trabalho mais simples.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Recurso de início frio aprimorado do pool de front-end

O Skype for Business Server apresenta um novo cmdlet que simplifica e melhora o processo de inicialização a frio de todo o pool de front-ends. Quando você usa o novo cmdlet **Start-CsPool** , ele verifica os pré-requisitos para todos os servidores front-end no pool e, em seguida, tenta iniciar cada servidor. Se encontrar problemas, ele os diagnostica e alerta você com detalhes e soluções alternativas. Em alguns casos, ele permite que você inicie o pool mesmo se alguns dos servidores individuais não puderem ser iniciados.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Suporte do SQL Server AlwaysOn para servidores locais

O Skype for Business Server 2015 adiciona suporte para os grupos de disponibilidade AlwaysOn do SQL Server e instâncias de cluster de failover do SQL Server AlwaysOn. Além desses recursos, o Skype for Business Server continua o suporte para espelhamento de banco de dados e cluster do SQL Server, como nas versões anteriores do Lync Server.
  
O SQL Server AlwaysOn Availability groups é uma solução de alta disponibilidade e recuperação de desastres no SQL Server 2012 e no SQL Server 2014 que oferece uma alternativa ao espelhamento de banco de dados. Um grupo de disponibilidade oferece suporte a um ambiente de failover para um conjunto discreto de bancos de dados (conhecidos como bancos de dados de disponibilidade) que fazem failover juntos. Um grupo de disponibilidade oferece suporte a um conjunto de bancos de dados principais de leitura e gravação de um a quatro conjuntos de bancos de dados secundários correspondentes. Opcionalmente, os bancos de dados secundários podem ser disponibilizados para acesso somente leitura e para algumas operações de backup.
  
As instâncias de cluster de failover do SQL Server aproveitam a funcionalidade do WSFC (Windows Server failover clustering) para fornecer alta disponibilidade local por meio de redundância no nível de instância do servidor — uma instância de cluster de failover (FCI). Um FCI é uma única instância do SQL Server instalada nos nós WSFC (clustering de failover do Windows Server) e, possivelmente, em várias sub-redes.
  
Para obter mais informações, consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Aprimoramentos de registro centralizado e solução de problemas para servidores locais

O serviço de registro em log centralizado é o ambiente de registro em log preferido para o Skype for Business Server 2015. Não há novos recursos desta versão, mas a confiabilidade e o desempenho foram aprimorados para o serviço e o agente de serviço de registro em log (ClsAgent. exe), que se comunica com o controlador e recebe comandos emitidos pelo administrador.
  
O Skype for Business Server 2015 usa cmdlets do Windows PowerShell para gerenciar os agentes de serviço de registro em log, Iniciar rastreamento e gerar relatórios. (O Lync Server 2013 usou o ClsController. exe para executar essas tarefas.)
  
O serviço de registro em log centralizado pode ser executado em qualquer Skype for Business Server 2015. Os cenários internos (rastreamentos predefinidos) permanecem os mesmos, assim como a capacidade de criar cenários personalizados. Há um cenário especial chamado AlwaysOn que está sempre em execução e permite que os administradores localizem problemas comuns quase em tempo real.
  
A ferramenta de depuração do Snooper também foi atualizada para permitir a depuração de logs de mobilidade e funcionará com dispositivos conectados ao Lync 2013 ou ao Skype for Business Server 2015. A ferramenta está disponível como um download da Web nas [ferramentas de depuração](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Implantação e gerenciamento híbridos

O Skype for Business Server 2015 habilita os recursos de gerenciamento e administração de implantação híbrida ao introduzir os seguintes recursos:
  
- Recomendações para implantações híbridas com base no estado dos ativos locais do cliente, conforme determinado pelo onramp for Office 365 Automated assistation Tool.
- Aprimoramentos no painel de controle do Skype for Business Server e no centro de administração do Skype for Business Server para que os administradores possam usar essas ferramentas para gerenciar uma implantação híbrida.
- Aprimoramentos do painel de controle que permitem que os administradores entrem em um locatário do Microsoft 365 ou do Office 365 e configurem o híbrido com o Skype for Business online usando o assistente de configuração híbrida.
- O painel de controle suporta para mover usuários locais para o Skype for Business online ou mover os usuários do Skype for Business online de volta para o local.
- Recursos do painel de controle para identificar e filtrar os objetos de usuário locais que foram movidos para o Skype for Business online (ou seja, usuários híbridos) de usuários locais.
- Recursos do centro de administração para identificar e filtrar os usuários de nuvem inicialmente criados no Skype for Business online de usuários híbridos migrados do local para o online.
- A capacidade de administrar usuários híbridos usando o painel de controle para propriedades gerenciáveis do centro de administração e local para propriedades gerenciáveis do Skype for Business online.
- Usando a sincronização de senha com DirSync, a capacidade de sincronizar senhas do Active Directory local com o locatário online. Se configurado, este recurso remove a necessidade de implantar o AD FS para autenticação federada, mas o AD FS ainda é necessário para a autenticação multifator. 
- Suporte contínuo para coexistência entre o Skype for Business Online e o Exchange local.
    
> [!NOTE]
> Não há nenhuma alteração na experiência de suporte e coexistência do Lync Online 2013 e do Exchange local. 
  
## <a name="multi-factor-authentication"></a>Autenticação multifator

A autenticação multifator é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada crítica de segurança a entradas e transações do usuário. Por exemplo, exigir um nome de usuário e uma senha e um certificado. O Skype for Business Server 2015 continua a criar os recursos de autenticação multifator disponíveis nas atualizações cumulativas do Lync Server 2013. As alterações significativas na autenticação multifator são:
  
- Uso da biblioteca de autenticação do Active Directory do Office 2013 SP1 para integração com o Exchange e o SharePoint
- Suporte para o recurso de autenticação multifator no cliente do Skype for Business Web App
    
Com a autenticação multifator do Skype for Business, agora é possível fornecer opções de autenticação diferentes com base na geografia. Por exemplo, os clientes podem configurar o ambiente para que a autenticação interna dependa da autenticação integrada do Windows, enquanto os funcionários que se autenticam de fora da organização usam a autenticação multifator. 
  
A experiência de autenticação multifator do Skype for Business é uniforme independentemente de:
  
- Localização geográfica: se o usuário está entrando de dentro ou fora da organização 
- Tipo de cliente/dispositivo – qual cliente do Skype for Business é usado e em qual dispositivo o cliente está executando (PC, Mobile, iPad, etc.)
- Local da conta: se o usuário está hospedado em um Active Directory local ou no Azure Active Directory online.
