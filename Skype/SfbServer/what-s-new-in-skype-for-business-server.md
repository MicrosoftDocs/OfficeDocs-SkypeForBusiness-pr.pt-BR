---
title: Novidades no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: "Resumo: Leia este tópico para conhecer os novos recursos do Skype para Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte que Lync agora é Skype para negócios – consulte What's new."
ms.openlocfilehash: e1ae2a046b955e83ccc7c811984a526c26f7c526
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "24961026"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novidades no Skype for Business Server 2015

**Resumo:** Leia este tópico para conhecer os novos recursos do Skype para Business Server 2015. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Lync está agora Skype para negócios – consulte What's new](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync agora é Skype para a plataforma de negócios, uma comunicação e colaboração que reúne uma experiência tendo como Skype com a segurança de nível empresarial, conformidade e controle do Lync. Skype para negócios oferece recursos incluindo presença, mensagens Instantâneas, voz e chamadas de vídeo e reuniões online. Skype para negócios fornece um novo cliente de experiência, uma nova versão do servidor e atualizações do serviço no Office 365. Se os usuários em sua organização já estiverem familiarizados com Skype, eles apreciará o poder e a simplicidade do Skype para negócios onde é fácil encontrar e conecte-se com seus colegas. Se os usuários em sua organização são provenientes para Skype para negócios Lync, eles reconhecerá todos os recursos que eles já usam mas em uma nova interface atualizada com controles e novas adições simplificados. Além da nova experiência do cliente, Skype para Business Server 2015 oferece vários novos recursos para melhorar a capacidade dos servidores locais e soluções híbridas.
  
Novos recursos do Skype para Business Server 2015 incluem melhorias:
  
- Experiência do usuário  
- Suporte a voz e vídeo
- Suporte a celular
- Gerenciamento de servidores locais
- Implantação e gerenciamento de soluções híbridas
- Suporte a autenticação multifator
    
## <a name="user-experience"></a>Experiência do usuário

O Skype para o cliente de negócios é muito semelhante para a versão do consumidor do Skype e usa o mesmo botões e ícones. Há menos menus e uma hierarquia de tarefas mais horizontal, o que torna mais fácil para os usuários encontrar rapidamente os controles e comandos de que precisam. 
  
Skype para negócios inclui a nova experiência de usuário descrito acima e a experiência do usuário Lync 2013 lançadas anteriormente. A inclusão de ambas as experiências permite às empresas gerenciar as alterações dos seus usuários controlando o processo e o vencimento do novo cliente distribuídas. A experiência do usuário padrão depende de qual versão do servidor que você está usando. Os administradores podem escolher a experiência preferida usando o cmdlet **Set-CsClientPolicy** com o parâmetro EnableSkypeUI. Para obter mais informações sobre como configurar a experiência do cliente, consulte [Configurar o cliente de experiência com Skype para negócios](deploy/deploy-clients/configure-the-client-experience.md) e [comparação de recursos do cliente de Desktop do Skype para negócios](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> A experiência do cliente Lync 2013 não é uma opção para Skype para as versões de cliente 2016 de negócios. Antes de tentar configurar seu ambiente do cliente para usar o cliente do Lync 2013, verifique a versão do cliente para garantir que ele não começa com o número de 16; Por exemplo: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Melhorias em voz e vídeo

Skype para Business Server 2015 inclui aprimoramentos a funcionalidade de voz e vídeo, inclusive a coleta de dados de chamada e análise e melhoria interoperabilidade com sistemas de teleconferência de vídeo de terceiros.
  
### <a name="call-data-collection-and-analysis"></a>Análise e coleta de dados da chamada

O taxa de chamada meu recurso permite Skype para administradores corporativos Server 2015 coleta dados de chamada. Esse recurso está disponível somente para implantações locais. Os usuários são solicitados a fazer uma pesquisa depois de encerrar uma chamada. Para mais informações, consulte [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Melhor interoperabilidade com sistemas de vídeo e teleconferência de terceiros

O servidor de interoperabilidade de vídeo (VIS) atua como um intermediário entre Skype para sistemas VTC (video teleconferencing) do servidor de negócios e Cisco. Ao ingressar em uma reunião, os usuários agora podem selecionar um sistema VTC da Cisco. O Servidor de Interoperabilidade de Vídeo (VIS) é implementado como uma função de servidor autônoma para implantações locais. Para obter mais informações, consulte [Planejar para o servidor de interoperabilidade de vídeo no Skype para Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Chamada via Trabalho

A recurso chamada via trabalho permite que os usuários corporativos fazer chamadas de voz usando o Skype para o cliente de negócios. Quando um usuário faz uma chamada de voz, ela é encaminhada do Skype for Business para telefone de PBX ou PSTN do originador. Assim que o originador atender o telefone, a chamada será direcionada para o número de destino. As respostas de destinatário da chamada e a chamada é estabelecida com Skype para atuando como o painel de controle de negócios. O originador pode gerenciar sua presença e controles de chamada do Skype para negócios. O administrador do servidor pode habilitar e configurar a Chamada via Trabalho para a empresa. Para obter mais informações, consulte [Plan for chamada Via trabalho no Skype para Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Melhorias no suporte a dispositivo móvel

Melhorias para o suporte a dispositivos móveis incluem recursos para melhorar a experiência móvel para usuários do Enterprise Edition, como o acesso aos dados de log e o histórico da conversa, experiências de reunião móvel avançada e suporte de logon único em Office. Além disso, há melhorias para suporte Android, melhorias de desempenho e recursos para simplificar a integração por meio da estrutura de aplicativo comuns. 
  
> [!NOTE]
> Servidores do Lync 2013 UCWA devem ser atualizados para Skype para negócios 2015 de servidor dar suporte a clientes móveis. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>O histórico de conversa no servidor agora está disponível para dispositivos móveis

Para habilitar o acesso móvel a dados de log de chamada, mensagens Instantâneas perdidas e histórico da conversa, arquivamento dessas informações é agora processado por meio do servidor para todos os clientes móveis. O recurso de aceitação automática para mensagens instantâneas melhora a confiabilidade ao evitar tempo limite no servidor quando um usuário móvel não responde a uma IM imediatamente. Para tirar proveito da integração de pastas do Exchange/Outlook baseado em servidor, o Exchange Server 2013 ou mais novos e atualizados de clientes móveis, são necessários. 
  
### <a name="enhanced-meeting-experiences"></a>Experiências aprimoradas de reunião

A funcionalidade de reunião no desktop agora também está disponível para usuários de dispositivos móveis. A nova funcionalidade inclui:
  
- Navegação assíncrona pelo conteúdo do PowerPoint compartilhado
- Capacidade do apresentador assumam o controle do PowerPoint compartilhado conteúdo
- Gerenciamento de lobby para apresentadores, permitindo que eles aceitem ou neguem participantes
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business no Android aprimoramentos

Skype for Business no Android agora oferece recursos semelhantes ao que está disponível em Skype for Business no iOS e Skype for Business no Windows:
  
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

Skype para Business Server 2015 oferece vários novos recursos para melhorar a capacidade de servidores no local, incluindo atualização in-loco, instalação inteligente, melhoria de aplicação de patch e atualização processa, maior capacidade de iniciar a frio de pool Front-End, o SQL Server AlwaysOn suporte e centralizado log e solução de problemas.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Atualização in-loco para servidores locais

Agora você pode atualizar sistemas do Lync Server 2013 para Skype para Business Server 2015 usando o novo in-loco recurso de atualização, que usa os investimentos existentes de hardware e servidor Lync Server 2013, reduzindo assim o custo total para implantar o Skype para Business Server 2015.
  
Há dois cenários para atualização in-loco: o método Mover Usuário, que não requer tempo de inatividade, e o método Offline, que requer tempo de inatividade. Para mais informações sobre qual desses procedimentos de atualização é o mais adequado para a sua empresa, consulte [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> A opção de in-loco não estará disponível se você estiver atualizando do Lync Server 2010. Para obter mais informações sobre como atualizar do Lync Server 2010, consulte [Planejar a atualização para Skype para Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Smart Setup

O recurso Smart Setup, que detecta e baixa automaticamente atualizações, agora faz parte do programa Setup. Durante o processo de instalação, será perguntado ao usuário se o processo de instalação deve verificar se há atualizações. Para mais informações, consulte [Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Processo aprimorado de aplicação de patch e atualização no Servidor Front-End

Skype para Business Server introduz dois novos cmdlets que ajudam a tornar atualizando ou aplicar o patch de servidores Front-End muito mais fácil do que nas versões anteriores do Microsoft Lync Server.
  
Quando você precisa aplicar um patch, ou realizar outra manutenção, para um servidor Front-End, simplesmente digite **Invoke-CsComputerFailOver** e especifique o nome desse servidor. Skype para Business Server move temporariamente a carga de trabalho desse servidor para os outros servidores no pool. Você pode fazer a manutenção e depois usar o cmdlet **Invoke-CsComputerFailback** para colocar aquele servidor de volta em serviço. Se você precisar aplicar um patch em cada servidor de um pool, siga este procedimento para cada servidor, um de cada vez. Esses novos cmdlets permitem que você aplique patches em servidores muito mais rapidamente do que em versões anteriores, e com mais confiabilidade e um fluxo de trabalho mais simples.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Capacidade aprimorada de inicialização a frio no Pool de Front-Ends

Skype para Business Server introduz um novo cmdlet que simplifica e melhora o processo de inicialização frio de um pool de Front-End inteiro. Quando você usa o novo cmdlet **Start-CsPool**, ele verifique os pré-requisitos para todos os Servidores Front-End no pool e, em seguida, tenta iniciar cada servidor. Se encontrar algum problema, ele faz o diagnóstico e envia a você um alerta com detalhes e soluções alternativas. Em alguns casos, ele permite que você inicie o pool mesmo se não for possível iniciar alguns de seus servidores.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Suporte do SQL Server AlwaysOn para servidores locais

Skype para Business Server 2015 adiciona suporte para grupos de disponibilidade AlwaysOn do SQL Server e instâncias de Cluster de Failover do SQL Server AlwaysOn. Além desses recursos, Skype para Business Server continua a fornecer suporte para espelhamento de banco de dados e SQL Server clustering, como nas versões anteriores do Microsoft Lync Server.
  
Grupos de disponibilidade AlwaysOn do SQL Server é uma solução de recuperação de desastres no SQL Server 2012 e SQL Server 2014 que fornece uma alternativa ao espelhamento de banco de dados e alta disponibilidade. Um grupo de disponibilidade oferece suporte a um ambiente de failover para um conjunto distinto de bancos de dados (conhecido como bancos de dados de disponibilidade) que o failover juntos. Um grupo de disponibilidade suporta um conjunto de bancos de dados principais de leitura-gravação e um a quatro conjuntos de bancos de dados secundários correspondentes. Opcionalmente, bancos de dados secundários podem ser disponibilizados para acesso somente leitura e para algumas operações de backup.
  
Instâncias de Cluster de Failover do SQL Server aproveitar a funcionalidade de Clustering de Failover do Windows Server (WSFC) para fornecer alta disponibilidade local por meio de redundância no nível de instância do servidor — uma instância de cluster de failover (FCI). Um FCI é uma única instância do SQL Server que está instalado em todos nós de cluster de Failover do Windows Server (WSFC) e, possivelmente, em diversas sub-redes.
  
Para obter mais informações, veja [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Melhorias na solução de problemas e registro em log centralizado para servidores locais

The Centralized Logging Service é o ambiente de log preferencial para Skype para Business Server 2015. Não há novos recursos nesta versão, mas a confiabilidade e o desempenho foram aprimorados tanto no serviço quanto no are no Agente de Serviço de Log Centralizado (ClsAgent.exe)--o executável do serviço que se comunica com o controlador e recebe comandos que são enviados pelo administrador.
  
Skype para Business Server 2015 usa os cmdlets do Windows PowerShell para gerenciar os agentes de serviço de registro em log, iniciar o rastreamento e gerar relatórios. (Lync Server 2013 usado ClsController.exe para executar essas tarefas.)
  
The Centralized Logging Service pode executar em qualquer Skype para Business Server 2015. Os cenários integrados (rastreamentos pré-definidos) permanecem os mesmos, assim como a capacidade para criar cenários personalizados. Há um cenário especial chamado AlwaysOn que está sempre em execução e permite que os administradores localizem problemas comuns praticamente em tempo real.
  
A ferramenta de depuração Snooper também foi atualizada para permitir a depuração de logs de mobilidade e funcionará com dispositivos se conectando ao Lync 2013 ou Skype para Business Server 2015. A ferramenta está disponível como download da Web em [Ferramentas de depuração](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Gerenciamento e implantação de soluções híbridas

Skype para Business Server 2015 habilita recursos de gerenciamento e administração da implantação híbrida, apresentando os seguintes recursos:
  
- Recomendações para implantações híbridas baseadas no estado de ativos do local do cliente, conforme determinado pela OnRamp for O365 ferramenta de ajuda automatizada.
- Aprimoramentos para o Skype para painel de controle do Business Server e do Skype para negócios Centro de administração de servidor para que os administradores podem usar essas ferramentas para gerenciar uma implantação híbrida.
- Controle os aprimoramentos de painel que permitem que administradores entrar em um locatário O365 e configure as híbrida com Skype para negócios Online usando o Assistente de configuração híbrida.
- Controle o suporte de painel para mover usuários locais para Skype para Business Online ou movendo Skype para usuários corporativos Online novamente para o local.
- Controle os recursos do painel para identificar e filtrar os objetos de usuário local que tiverem sido movidos para Skype para negócios Online (ou seja, usuários híbridos) a partir de usuários locais.
- Recursos do Centro de administração para identificar e filtrar os usuários na nuvem inicialmente criados na Skype para Business Online dos usuários híbrida migrado do local como Online.
- A capacidade de administrar usuários híbridos usando o painel de controle para propriedades gerenciáveis de locais e do Centro de administração para propriedades gerenciáveis do Skype para Business Online.
- Uso de sincronização de senha com DirSync, a capacidade de sincronizar senhas do Active Directory local com o locatário online. Se configurado, esse recurso remove a necessidade de implantar AD FS para autenticação federada, mas o AD FS ainda é obrigatório para autenticação multifator. 
- Continua o suporte para a coexistência entre o Skype para Business Online e Exchange local.
    
> [!NOTE]
> Não há nenhuma alteração entre o Lync Online 2013 e Exchange local coexistência e suporte experiência. 
  
## <a name="multi-factor-authentication"></a>Autenticação multifator

A autenticação multifator é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada crítica de segurança às transações e autenticações de usuário. Por exemplo, exigência de nome de usuário e senha, bem como um certificado. Skype para Business Server 2015 continua a aproveitar os recursos de autenticação multifator disponíveis nas atualizações do Lync Server 2013 cumulativa. As mudanças significativas na autenticação multifator são:
  
- Uso da Biblioteca de Autenticação do Active Directory do Office 2013 SP1 para integração com o Exchange e o SharePoint
- Suporte para o recurso de autenticação multifator no Skype para cliente corporativos Web App
    
Com Skype para autenticação de vários fatores comerciais, é possível fornecer opções de autenticação diferentes com base na região geográfica. Por exemplo, consumidores podem configurar seus ambientes para que a autenticação interna dependa da autenticação integrada do Windows, enquanto funcionários autenticando a partir de um local fora da organização utilizam a autenticação multifator. 
  
O Skype para experiência do Business a autenticação multifator é perfeita independentemente de:
  
- Localização geográfica - se o usuário estiver entrando de dentro ou fora da organização 
- Tipo de dispositivo do cliente - qual Skype para o cliente de negócios é usado e qual dispositivo o cliente está sendo executado em (PC, mobile, iPad, etc.)
- Conta local - se o usuário está hospedado em um local no Active Directory ou no Windows Azure Active Directory Online (O365)