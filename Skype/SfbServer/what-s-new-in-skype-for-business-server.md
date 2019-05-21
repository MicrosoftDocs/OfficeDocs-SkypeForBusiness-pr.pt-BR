---
title: Novidades no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Resumo: Leia este tópico para saber mais sobre os novos recursos do Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte o Lync agora é o Skype for Business, confira o que há de novo.'
ms.openlocfilehash: e59d158242a5d2dd4b129da3a531749b22e3eadc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291512"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novidades no Skype for Business Server 2015

**Resumo:** Leia este tópico para saber mais sobre os novos recursos do Skype for Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte o [Lync agora é o Skype for Business, confira o que há de novo](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
O Lync agora é o Skype for Business, uma plataforma de comunicação e colaboração que reúne uma experiência inspirada pela Skype com a segurança de nível empresarial, a conformidade e o controle do Lync. O Skype for Business oferece recursos, incluindo presença, mensagens de chat, chamadas de voz e com vídeo e reuniões online. O Skype for Business oferece uma nova experiência de cliente, uma nova versão do servidor e atualizações para o serviço do Office 365. Se os usuários da sua organização já estiverem familiarizados com o Skype, eles apreciarão o poder e a simplicidade do Skype for Business, onde é fácil encontrar e se conectar com os colegas de trabalho. Se os usuários da sua organização estiverem chegando ao Skype for Business a partir do Lync, eles reconhecerão todos os recursos que já usam, mas em uma nova interface com controles simplificados e novas adições. Além da nova experiência do cliente, o Skype for Business Server 2015 oferece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais e soluções híbridas.
  
Os novos recursos do Skype for Business Server 2015 incluem melhorias em:
  
- Experiência do usuário  
- Suporte a voz e vídeo
- Suporte a celular
- Gerenciamento de servidores locais
- Implantação e gerenciamento de soluções híbridas
- Suporte a autenticação multifator
    
## <a name="user-experience"></a>Experiência do usuário

O cliente Skype for Business é muito semelhante à versão de consumidor do Skype e usa os mesmos botões e ícones. Há menos menus e uma hierarquia de tarefas mais horizontal, o que torna mais fácil para os usuários encontrar rapidamente os controles e comandos de que precisam. 
  
O Skype for Business inclui a nova experiência do usuário descrita acima e a experiência do usuário do Lync 2013 lançada anteriormente. A inclusão de ambas as experiências permite que as empresas gerenciem alterações para seus usuários controlando o processo e a temporização da nova distribuição do cliente. A experiência do usuário padrão depende da versão do servidor que você está usando. Os administradores podem escolher a experiência preferida usando o cmdlet **Set-CsClientPolicy** com o parâmetro EnableSkypeUI. Para obter mais informações sobre como configurar a experiência do cliente, consulte [Configurar a experiência do cliente com o Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) e o [recurso de cliente de área de trabalho para o Skype for Business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> A experiência do cliente do Lync 2013 não é uma opção para versões do cliente do Skype for Business 2016. Antes de tentar configurar o ambiente do cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não comece com o número 16; por exemplo: 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Melhorias em voz e vídeo

O Skype for Business Server 2015 inclui melhorias para a funcionalidade de voz e vídeo, incluindo análise e coleta de dados de chamadas e interoperabilidade aprimorada com sistemas de teleconferência de vídeo de terceiros.
  
### <a name="call-data-collection-and-analysis"></a>Análise e coleta de dados da chamada

O recurso classificar minha chamada permite que os administradores do Skype for Business Server 2015 coletem dados de chamadas. Esse recurso está disponível somente para implantações locais. Os usuários são solicitados a fazer uma pesquisa depois de encerrar uma chamada. Para mais informações, consulte [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Melhor interoperabilidade com sistemas de vídeo e teleconferência de terceiros

O servidor de interoperabilidade de vídeo (VIS) atua como intermediário entre os sistemas Skype for Business Server e Cisco Video teleconferência (VTC). Ao ingressar em uma reunião, os usuários agora podem selecionar um sistema VTC da Cisco. O Servidor de Interoperabilidade de Vídeo (VIS) é implementado como uma função de servidor autônoma para implantações locais. Para obter mais informações, consulte [planejar o servidor de interoperabilidade de vídeo no Skype for Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Chamada via Trabalho

A chamada via recurso de trabalho permite que os usuários corporativos façam chamadas de voz do cliente Skype for Business. Quando um usuário faz uma chamada de voz, ele é encaminhado do Skype for Business para o PBX ou telefone PSTN do originador. Assim que o originador atender o telefone, a chamada será direcionada para o número de destino. As respostas do destinatário da chamada e a chamada são estabelecidas com o servidor do Skype for Business, como o painel de controle. O originador pode gerenciar a presença e os controles de chamada do Skype for Business. O administrador do servidor pode habilitar e configurar a Chamada via Trabalho para a empresa. Para obter mais informações, consulte [planejar chamada via trabalho no Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Melhorias no suporte a dispositivo móvel

Melhorias no suporte a dispositivos móveis incluem recursos para melhorar a experiência móvel dos usuários da edição Enterprise, como acesso a histórico de conversas e dados de log, experiências aprimoradas de reunião móvel e suporte ao logon único no Office. Além disso, há melhorias no suporte ao Android, melhorias de desempenho e recursos para simplificar a integração por meio da estrutura de aplicativos comum. 
  
> [!NOTE]
> O Lync 2013 UCWA Servers deve ser atualizado para o Skype for Business Server 2015 para dar suporte a clientes móveis. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>O histórico de conversa no servidor agora está disponível para dispositivos móveis

Para habilitar o acesso móvel ao histórico de conversas, mensagens de chat perdidas e dados de registro de chamadas, o arquivamento dessas informações é processado por meio do servidor para todos os clientes móveis. O recurso de aceitação automática para mensagens instantâneas melhora a confiabilidade ao evitar tempo limite no servidor quando um usuário móvel não responde a uma IM imediatamente. Para aproveitar as vantagens da integração de pastas do Exchange/Outlook baseadas em servidor, Exchange Server 2013 ou mais recente e clientes móveis atualizados, são necessários. 
  
### <a name="enhanced-meeting-experiences"></a>Experiências aprimoradas de reunião

A funcionalidade de reunião no desktop agora também está disponível para usuários de dispositivos móveis. A nova funcionalidade inclui:
  
- Navegação assíncrona pelo conteúdo do PowerPoint compartilhado
- A capacidade do apresentador assumir o controle do conteúdo compartilhado do PowerPoint
- Gerenciamento de lobby para apresentadores, permitindo que eles aceitem ou neguem participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business para melhorias no Android

O Skype for Business no Android agora oferece recursos semelhantes ao que está disponível no Skype for Business no iOS e no Skype for Business no Windows:
  
- Continuar ou reingressar em conversas
- Habilitar autentificação de certificado e passiva
- Convidar outras pessoas para uma conversa
- Iniciar facilmente grupos de conversa
- Participar de uma reunião sem ser usuário do Skype for Business
- Habilitar UI do smartphone em tablets Android
- Gerenciar reuniões adicionando ou removendo participantes
    
> [!NOTE]
> Esses recursos exigem a versão 4.0 ou superior do sistema operacional Android. 
  
## <a name="management-of-on-premises-servers"></a>Gerenciamento de servidores locais

O Skype for Business Server 2015 oferece vários novos recursos para melhorar a capacidade de gerenciamento de servidores locais, incluindo atualização in-loco, configuração inteligente, patches e processos de atualização aprimorados, recurso de início frio aprimorado do pool de front-end, SQL Server AlwaysOn suporte e registro em log e solução de problemas centralizados.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Atualização in-loco para servidores locais

Agora você pode atualizar os sistemas do Lync Server 2013 para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco, que usa o Lync Server 2013 do Lync Server e investimentos em servidor e, assim, reduz o custo geral para implantar o Skype for Business Server 2015.
  
Há dois cenários para atualização in-loco: o método Mover Usuário, que não requer tempo de inatividade, e o método Offline, que requer tempo de inatividade. Para mais informações sobre qual desses procedimentos de atualização é o mais adequado para a sua empresa, consulte [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> A opção in-loco não estará disponível se você estiver atualizando do Lync Server 2010. Para obter mais informações sobre a atualização do Lync Server 2010, consulte [planejar a atualização para o Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Smart Setup

O recurso Smart Setup, que detecta e baixa automaticamente atualizações, agora faz parte do programa Setup. Durante o processo de instalação, será perguntado ao usuário se o processo de instalação deve verificar se há atualizações. Para mais informações, consulte [Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Processo aprimorado de aplicação de patch e atualização no Servidor Front-End

O Skype for Business Server introduz dois cmdlets novos que ajudam a facilitar a atualização ou o patch dos servidores front-end do que nas versões anteriores do Lync Server.
  
Quando você precisar aplicar um patch ou executar qualquer outra manutenção, em um servidor front-end, basta digitar **Invoke-CsComputerFailOver** e especificar o nome do servidor. O Skype for Business Server move a carga de trabalho desse servidor temporariamente para os outros servidores do pool. Você pode fazer a manutenção e depois usar o cmdlet **Invoke-CsComputerFailback** para colocar aquele servidor de volta em serviço. Se você precisar aplicar um patch em cada servidor de um pool, siga este procedimento para cada servidor, um de cada vez. Esses novos cmdlets permitem que você aplique patches em servidores muito mais rapidamente do que em versões anteriores, e com mais confiabilidade e um fluxo de trabalho mais simples.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Capacidade aprimorada de inicialização a frio no Pool de Front-Ends

O Skype for Business Server introduz um novo cmdlet que simplifica e melhora o processo de início frio de todo o pool de front-end. Quando você usa o novo cmdlet **Start-CsPool**, ele verifique os pré-requisitos para todos os Servidores Front-End no pool e, em seguida, tenta iniciar cada servidor. Se encontrar algum problema, ele faz o diagnóstico e envia a você um alerta com detalhes e soluções alternativas. Em alguns casos, ele permite que você inicie o pool mesmo se não for possível iniciar alguns de seus servidores.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Suporte do SQL Server AlwaysOn para servidores locais

O Skype for Business Server 2015 adiciona suporte para os grupos de disponibilidade do SQL Server AlwaysOn e instâncias de cluster de failover do SQL Server AlwaysOn. Além desses recursos, o Skype for Business Server continua a oferecer suporte ao espelhamento de banco de dados e ao agrupamento do SQL Server, como nas versões anteriores do Lync Server.
  
Os grupos de disponibilidade do SQL Server AlwaysOn são uma solução de alta disponibilidade e recuperação de desastres no SQL Server 2012 e no SQL Server 2014 que fornecem uma alternativa ao espelhamento do banco de dados. Um grupo de disponibilidade dá suporte a um ambiente de failover para um conjunto discreto de bancos de dados (conhecidos como bancos de dados de disponibilidade) que falham juntos. Um grupo de disponibilidade dá suporte a um conjunto de bancos de dados primários leitura-gravação e a um a quatro conjuntos de bancos de dados secundários correspondentes. Opcionalmente, bancos de dados secundários podem ser disponibilizados para acesso somente leitura e para algumas operações de backup.
  
Instâncias de cluster de failover do SQL Server aproveitam a funcionalidade do WSFC (Windows Server failover clustering) para fornecer alta disponibilidade local por meio de redundância no nível de instância do servidor – uma instância de cluster de failover (FCI). Um FCI é uma instância única do SQL Server instalada em nós WSFC (Windows Server failover clustering) e, possivelmente, em várias sub-redes.
  
Para obter mais informações, veja [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Melhorias na solução de problemas e registro em log centralizado para servidores locais

O serviço de log centralizado é o ambiente de registro em log preferencial para o Skype for Business Server 2015. Não há novos recursos nesta versão, mas a confiabilidade e o desempenho foram aprimorados tanto no serviço quanto no are no Agente de Serviço de Log Centralizado (ClsAgent.exe)--o executável do serviço que se comunica com o controlador e recebe comandos que são enviados pelo administrador.
  
O Skype for Business Server 2015 usa cmdlets do Windows PowerShell para gerenciar os agentes de serviço de log, iniciar o rastreamento e gerar relatórios. (O Lync Server 2013 usou ClsController. exe para executar essas tarefas.)
  
O serviço de registro centralizado pode ser executado em qualquer Skype for Business Server 2015. Os cenários integrados (rastreamentos pré-definidos) permanecem os mesmos, assim como a capacidade para criar cenários personalizados. Há um cenário especial chamado AlwaysOn que está sempre em execução e permite que os administradores localizem problemas comuns praticamente em tempo real.
  
A ferramenta de depuração de rastreamento também foi atualizada para permitir a depuração de logs de mobilidade e funcionará com dispositivos que se conectam ao Lync 2013 ou ao Skype for Business Server 2015. A ferramenta está disponível como um download da Web em [ferramentas de depuração](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Gerenciamento e implantação de soluções híbridas

O Skype for Business Server 2015 permite recursos de administração e gerenciamento de implantação híbrida introduzindo os seguintes recursos:
  
- Recomendações para implantações híbridas com base no estado dos ativos locais do cliente, conforme determinado pela ferramenta de assistência automatizada da onrampa do O365.
- Aprimoramentos para o painel de controle do Skype for Business Server e o centro de administração do Skype for Business Server para que os administradores possam usar essas ferramentas para gerenciar uma implantação híbrida.
- Aprimoramentos do painel de controle que permitem aos administradores entrarem em um locatário do O365 e configurar híbrido com o Skype for Business online usando o assistente de configuração híbrida.
- Suporte ao painel de controle para mover usuários locais para o Skype for Business online ou mover os usuários do Skype for Business online de volta para o local.
- Recursos do painel de controle para identificar e filtrar objetos de usuário locais que foram movidos para o Skype for Business online (ou seja, usuários híbridos) de usuários locais.
- Recursos do centro de administração para identificar e filtrar os usuários da nuvem inicialmente criados no Skype for Business online a partir de usuários híbridos migrados de usuários locais para online.
- A capacidade de administrar usuários híbridos usando o painel de controle para propriedades gerenciáveis no local e no centro de administração de propriedades que podem ser gerenciados a partir do Skype for Business online.
- Uso de sincronização de senha com DirSync, a capacidade de sincronizar senhas do Active Directory local com o locatário online. Se configurado, esse recurso remove a necessidade de implantar AD FS para autenticação federada, mas o AD FS ainda é obrigatório para autenticação multifator. 
- Suporte contínuo para a coexistência entre o Skype for Business Online e o Exchange no local.
    
> [!NOTE]
> Não há nenhuma alteração na 2013 do Lync Online e na experiência de suporte e de coexistência do Exchange local. 
  
## <a name="multi-factor-authentication"></a>Autenticação multifator

A autenticação multifator é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada crítica de segurança às transações e autenticações de usuário. Por exemplo, exigência de nome de usuário e senha, bem como um certificado. O Skype for Business Server 2015 continua a compilar os recursos de autenticação multifator disponíveis nas atualizações cumulativas do Lync Server 2013. As mudanças significativas na autenticação multifator são:
  
- Uso da Biblioteca de Autenticação do Active Directory do Office 2013 SP1 para integração com o Exchange e o SharePoint
- Suporte para o recurso de autenticação multifator no cliente do Skype for Business Web App
    
Com a autenticação multifator do Skype for Business, agora é possível fornecer opções de autenticação diferentes com base na geografia. Por exemplo, consumidores podem configurar seus ambientes para que a autenticação interna dependa da autenticação integrada do Windows, enquanto funcionários autenticando a partir de um local fora da organização utilizam a autenticação multifator. 
  
A experiência de autenticação multifator do Skype for Business é perfeita, independentemente de:
  
- Localização geográfica-se o usuário estiver entrando de dentro ou de fora da organização 
- Tipo de cliente/dispositivo – qual cliente do Skype for Business é usado e em qual dispositivo o cliente está executando (PC, celular, iPad etc.)
- Local da conta: se o usuário estiver hospedado em um Active Directory local ou no Microsoft Azure Active Directory online (O365)
