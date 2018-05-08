---
title: Planejar a resiliência do Enterprise Voice no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Saiba como suporte a resiliência de voz em Skype para Business Server Enterprise Voice, em sites centrais e sites de filiais. Opções de site de filial incluem Implantando aparelhos de filial persistente ou servidores de filial persistente.
ms.openlocfilehash: f5497c31e407d5d03564ab7caf7a0b8c8d4e0914
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server-2015"></a>Planejar a resiliência do Enterprise Voice no Skype for Business Server 2015
 
Saiba como suporte a resiliência de voz em Skype para Business Server Enterprise Voice, em sites centrais e sites de filiais. Opções de site de filial incluem Implantando aparelhos de filial persistente ou servidores de filial persistente.
  
Resiliência de voz refere-se à capacidade de usuários para continuar fazendo e recebendo chamadas se um site central que hospeda Skype para Business Server fica indisponível, seja por meio de uma longa distância (WAN) falha ou outra causa de rede. Se um local central falhar, o serviço do Enterprise Voice deverá continuar sem interrupções por meio de failover direto para um local de backup. No caso de uma falha de WAN, as chamadas do local de filial deverão ser redirecionadas para um gateway PSTN local. Esta seção discute o planejamento de resiliência de voz no caso de uma falha do local central ou de WAN.
  
## <a name="central-site-resiliency"></a>Resiliência do local central

Cada vez mais, as empresas possuem vários sites espalhados por todo o mundo. Manutenção de serviços de emergência, acesso para ajudar a equipe de assistência técnica e a capacidade de realizar tarefas essenciais aos negócios quando um site central estiver fora de serviço é essencial para qualquer solução de resiliência do Enterprise Voice. Quando um site central torna-se indisponível, as seguintes condições devem ser atendidas:
  
- O failover de voz deve ser fornecido.
    
- Usuários que normalmente registrar com o pool de Front-End no site central devem ser capazes de registrar com uma alternativa pool Front-End. Isso pode ser feito criando SRV de DNS vários registros, cada um deles resolve para um pool de diretor ou o pool de Front-End em cada um dos seus locais centrais. Você pode ajustar a prioridade e os níveis de importância dos registros SRV para que os usuários que são atendidos por site central obtenham o pool de diretor e Front-End correspondente à frente dos outros registros SRV.
    
- As chamadas para/de usuários localizados em outros sites devem ser reencaminhadas para a PSTN.
    
Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.
  
### <a name="architecture-and-topology"></a>Arquitetura e topologia

Planejando a resiliência de voz em um site central exige noções básicas da função central reproduzida pelo Skype para negócios servidor registrador em Habilitar o failover de voz. O Skype para negócios servidor registrador é um serviço que permite que o registro de cliente e de autenticação e fornece serviços de roteamento. Ele é executado em todos os servidores Standard Edition, servidor Front-End, diretor ou aparelho de filial persistente. Um pool de registradores consiste em serviços em execução no pool Front-End e que reside no mesmo site do registrador. Um Skype para o cliente de negócios descobre pool Front-End através do mecanismo de descoberta a seguir: 
  
1. Registro SRV de DNS
    
2. Serviço Web de Descoberta Automática 
    
3. Opção 120 do DHCP
    
Depois que o Skype para o cliente de negócios se conecta ao pool Front-End, ela é direcionada pelo Balanceador de carga para um dos servidores Front-End no pool. Se o servidor Front-End, por sua vez, redireciona o cliente para um registrador preferido no pool.
  
Cada usuário habilitado para o Enterprise Voice é atribuído a um determinado pool de registrador, que se torna o pool de registradores primário desse usuário. Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de Registradores Avançados primário. Para calcular o consumo de recursos do site central pelos usuários do site de filial que dependem do site central para presença, conferência ou failover, recomendamos considerar cada usuário do site de filial como se fosse um usuário registrado no site central. No momento, não há nenhum limite no número de usuários do site de filial, incluindo usuários registrados com um aparelho de filial persistente.
  
Para garantir a resiliência de voz em caso de uma falha do site central, o pool de Registradores Avançados primário deve ter um único pool de Registradores Avançados de backup designado localizado em outro site. O backup pode ser configurado usando as configurações de resiliência do construtor de topologias. Supondo que haja um link WAN resiliente entre os dois sites, os usuários cujo pool de Registradores Avançados primário não está mais disponível serão direcionados automaticamente para pool de backup.
  
As etapas a seguir descrevem o processo de descoberta e registro de clientes:
  
1. Um cliente descobre Skype para Business Server por meio de registros SRV de DNS. No Skype para Business Server, os registros SRV de DNS podem ser configurados para retornar mais de um FQDN à consulta SRV de DNS. Por exemplo, se a empresa Contoso tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de Diretores em cada um desses sites, os registros DNS SRV poderão apontar para os FQDNs do pool de Diretores em cada um dos três locais. Desde que o pool de diretor em um dos locais estiver disponível, o cliente pode se conectar para o primeiro salto Skype para Business Server.
    
    > [!NOTE]
    > Uso de um pool de diretor é opcional. Um pool de Front-End pode ser usado em vez disso. 
  
2. Pool de diretores informa o Skype para o cliente de negócios sobre o pool de registradores primário do usuário e o pool de registrador de backup.
    
3. O Skype para o cliente de negócios tenta conectar ao pool de registradores primário do usuário pela primeira vez. Se esse pool estiver disponível, o Registrador Avançado aceitará o registro. Se o pool de registradores primário não estiver disponível, o Skype para o cliente de negócios tenta se conectar ao pool de registrador de backup. Se o pool de registradores de backup está disponível e determinou que o pool de registradores primário do usuário está indisponível (detectando falta de pulsação por um intervalo especificado de failover) pool de registrador de backup aceita o registro do usuário. Depois que o Registrador Avançado de backup detectar que o Registrador Avançado primário está novamente disponível, o pool de backup redirecionará os clientes de failover para seu pool primário.
    
### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Os seguintes requisitos e recomendações para a implementação da resiliência de voz do site central são apropriados para a maioria das organizações:
  
- Os sites nos quais residem os pools de Registradores Avançados primário e de backup devem estar conectados por um link WAN resiliente.
    
- Cada site central deve conter um pool de Registradores Avançados que consiste em um ou mais Registradores Avançados.
    
- Cada pool de Registradores Avançados deve ter sua carga balanceada por meio do balanceamento de carga DNS, do balanceamento de carga de hardware ou de ambos. Para obter informações detalhadas sobre como planejar sua configuração de balanceamento de carga, consulte [requisitos de carga balanceamento para Skype para negócios](../../plan-your-deployment/network-requirements/load-balancing.md).
    
- Cada usuário deve ser atribuído a um pool de registradores primário usando qualquer um do Skype para o cmdlet **set-CsUser** de negócios Server Management Shell ou o Skype para painel de controle do Business Server.
    
- O pool primário deve ter um único pool de backup localizado em um site central diferente. 
    
- O pool de Registradores Avançados primário deve ser configurado de modo que seja feito o seu failover para o pool de Registradores Avançados de backup. Por padrão, o Registrador primário é definido para que esse failover ocorra após um intervalo de 300 segundos. Você pode alterar esse intervalo usando o Skype para o construtor de topologia de servidor de negócios.
    
- Configure uma rota de failover. Ao configurar a rota, especifique um gateway que está localizado em um site diferente do gateway especificado na rota primária.
    
- Se o site central contidos seu servidor de gerenciamento primário e o site está provavelmente para baixo por um longo período, você precisará reinstalar suas ferramentas de gerenciamento no local de backup; Caso contrário, não será possível alterar as configurações de gerenciamento.
    
### <a name="dependencies"></a>Dependências

Skype para Business Server depende os seguintes componentes de software e infraestrutura para garantir a resiliência de voz:
  
|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolver registros SRV e registros A para conectividade de servidor-servidor e servidor-cliente  <br/> |
|Exchange e Serviços Web do Exchange (EWS)  <br/> |Armazenamento de contatos; dados do calendário  <br/> |
|Unificação de Mensagens do Exchange e Serviços Web do Exchange  <br/> |Logs de chamada, lista de caixas postais, caixa postal  <br/> |
|Opções 120 do DHCP  <br/> |Se o DNS SRV não estiver disponível, o cliente tentará usar a Opção 120 do DHCP para descobrir o Registrador Avançado. Para que isso funcione, um servidor DHCP deve ser configurado ou Skype para negócios servidor DHCP deve ser habilitada.  <br/> |
   
### <a name="survivable-voice-features"></a>Recursos de voz persistente

Se os requisitos e as recomendações anteriores tiverem sido implementados, os seguintes recursos de voz serão fornecidos pelo pool de Registradores Avançados de backup:
  
- Chamadas PSTN de saída
    
- Chamadas PSTN de entrada, se o provedor de serviços de telefonia oferecer suporte ao failover para um site de backup
    
- Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes
    
- Administração básica de chamadas, incluindo espera, recuperação e transferência de chamadas
    
- Mensagens instantâneas entre dois participantes e compartilhamento de áudio e vídeo entre usuários no mesmo site
    
- Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamadas e serviços de chamada de equipe, mas somente se as duas partes da delegação de chamadas, ou todos os membros da equipe, estiverem configurados no mesmo site.
    
- Os clientes e telefones existentes continuam funcionando.
    
- Registro de detalhes das chamadas (CDR)
    
- Autenticação e autorização
    
Dependendo de como são configurados, os seguintes recursos de voz podem ou não funcionar quando um site central primário está fora de serviço:
  
- Depósito e recuperação de caixa postal 
    
    Se você desejar disponibilizar o UM do Exchange quando o site central primário estiver fora de serviço, deverá fazer o seguinte:
    
  - Altere os registros DNS SRV para que os servidores do UM do Exchange no site central apontem para os servidores de backup do UM do Exchange em outro site.
    
  - Configure Exchange UM plano de discagem para incluir servidores UM do Exchange no nível do site central e o site de backup, mas designar os servidores de backup UM do Exchange como desabilitada. do cada usuário Se o site principal ficar indisponível, o administrador do Exchange tem que marcar os servidores UM do Exchange no local de backup como ativadas.
    
    Se nenhuma das soluções anteriores for possível, em seguida, UM do Exchange não estará disponível no caso do site central se tornar indisponível.
    
- Conferência de todos os tipos
    
    Um usuário que fez failover para um site de backup pode ingressar em uma conferência criada ou hospedada por um organizador cujo pool está disponível, mas não pode criar nem hospedar uma conferência no seu próprio pool primário, que não está mais disponível. Da mesma forma, outros usuários não conseguem ingressar em conferências hospedadas no pool primário do usuário afetado.
    
Os seguintes recursos de voz não funcionam quando um site central primário está fora de serviço:
  
- Atendedor Automático de Conferência
    
- Roteamento baseado em DND e presença
    
- Atualização de configurações de encaminhamento de chamadas
    
- Serviço de Grupo de Resposta e Estacionamento de Chamada
    
- Provisionamento de novos telefones e clientes
    
- Pesquisa do Catálogo de Endereços na Web
    
## <a name="branch-site-resiliency"></a>Resiliência do site de filial

Se você deseja fornecer resiliência em filiais, ou seja, serviço de Enterprise Voice de alta disponibilidade, você tem três opções para fazer isso:
  
- Aparelho de Filial Persistente
    
- Servidor de Filial Persistente
    
- Um Skype completa para a implantação de servidor de negócios no site da filial 
    
Este guia ajudará você a avaliar qual solução de resiliência é melhor para a organização e, com base em sua solução de resiliência, a solução de conectividade PSTN a ser usada. Ele também o ajuda a se preparar para implantar a solução escolhida, descrevendo os pré-requisitos e outras considerações de planejamento.
  
### <a name="branch-site-resiliency-features"></a>Recursos de resiliência do site de filial

Se você fornecer resiliência em filiais, se a conexão de WAN de um site filial para um site central falhar ou se o site central está inacessível, os seguintes recursos de voz devem continuar a ser disponíveis:
  
- Chamadas de rede de telefonia pública comutada (PSTN) de entrada e saída
    
- Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes
    
- Administração básica de chamadas, incluindo espera, recuperação e transferência de chamadas
    
- Mensagens instantâneas de dois participantes
    
- Encaminhamento de chamadas, toques simultâneos de pontos de extremidade, delegação de chamadas e serviços de chamada de equipe, mas somente se o delegator e representante (por exemplo, um gerente e administrador do gerente) ou todos os membros da equipe estiverem configurados no mesmo site
    
- Registros de detalhes de chamadas (CDRs)
    
- Conferência de discagem PSTN com Atendedor Automático de Conferência
    
- Recursos de caixa postal, se forem configuradas definições de reroteamento de caixa postal.
    
- Autenticação e autorização de usuário
    
Os recursos a seguintes estarão disponíveis somente se sua solução de resiliência for uma larga escala Skype para implantação de servidor de negócios no site da filial:
  
- Conferências de IM, webconferências e conferências de A/V
    
- Presença e roteamento baseado em Não Incomodar (DND), onde as chamadas não tocam em extensões com o DND ativado
    
- Atualização de configurações de encaminhamento de chamadas
    
- Aplicativo grupo de resposta e aplicativo de estacionamento de chamada
    
- Provisionamento de novos telefones e clientes, mas apenas se o Active Directory Domain Services está presente no site da filial.
    
- 9-1-1 Avançado (E9-1-1)
    
    Se E9-1-1 é implantado e o tronco SIP no site central não está disponível porque o link de WAN está inoperante, o aparelho de filial persistente roteará chamadas de E9-1-1 para o gateway de local de filial. Para habilitar esse recurso, as políticas de voz dos usuários de filiais devem rotear chamadas para o gateway local em caso de falha de WAN.
    
> [!NOTE]
> O SBA (aparelho de filial persistente) não tem suporte no XMPP. Os usuários hospedados em um SBA configurações não será capazes de enviar mensagens instantâneas ou vejam a presença com contatos XMPP. 
  
### <a name="branch-site-resiliency-solutions"></a>Soluções de resiliência do site de filial

A resiliência de sites de filial proporciona vantagens evidentes à sua organização. Especificamente, se você perder a conexão para o site central, os usuários do site de filial continuará a ter o Enterprise Voice service e caixa postal (se você configurar definições de reencaminhamento de caixa postal). Entretanto, em sites com menos de 25 usuários, a solução de resiliência poderá não gerar um retorno adequado sobre o investimento. 
  
Há três opções para fornecer a resiliência do site de filial. A tabela a seguir o ajudará a determinar qual opção é a melhor para sua organização.
  
|**Se você …**|**Recomendamos que você use um …**|
|:-----|:-----|
|Hospedar entre 25 e 1.000 usuários no seu site de filial e se o retorno sobre o investimento não permitir uma implantação completa ou quando não houver suporte administrativo local disponível  <br/> |Aparelho de Filial Persistente  <br/> O aparelho de filial persistente é um servidor blade padrão do setor com um Skype para negócios servidor registrador e o servidor de mediação em execução no Windows Server 2008 R2. O aparelho de filial persistente também contém um gateway PSTN (rede) telefônica pública comutada. Dispositivos qualificados de terceiros (desenvolvidos por parceiros da Microsoft no programa de qualificação/certificação SBA [Aparelho de Filial Persistente]) fornecem uma conexão PSTN contínua em caso de falha da WAN, mas essa abordagem não oferece presença e conferência resilientes porque esses recursos dependem dos Servidores Front-End do site central.  <br/> Para obter detalhes sobre os aparelhos de filial persistente, consulte "Detalhes de aparelho de filial persistente", mais adiante neste tópico.  <br/> **Observação:** Se você decidir usar também um tronco SIP com seu aparelho de filial persistente, contate o fornecedor de aparelho de filial persistente para aprender sobre qual provedor de serviços é mais adequado para sua organização. <br/> |
|Hospede entre 1.000 e 2.000 usuários no seu site de filial, não têm uma conexão WAN resiliente e tendo treinado Skype para administradores do servidor de negócios disponíveis  <br/> |Servidor de filial persistente ou dois aparelhos de filial persistente.  <br/> O servidor de filial persistente é um servidor de Windows atender aos requisitos de hardware especificado que tem Skype para negócios servidor registrador e o servidor de mediação software instalado nele. Ele deve estar conectado a um provedor de serviços telefônicos por meio de um gateway PSTN ou de um tronco SIP.  <br/> Para obter detalhes sobre servidores de filial persistente, consulte "Detalhes de servidor de filial persistente", mais adiante neste tópico.  <br/> |
|Se você precisar de recursos de presença e conferência nos além Voice dos recursos para até 5.000 usuários e treinou Skype para administradores do servidor de negócios disponíveis  <br/> |Implante como um site central com um servidor Standard Edition e não como um site de filial.  <br/> Um larga escala Skype para implantação Business Server fornece uma conexão de PSTN contínua e presença resiliente e conferência em caso de falha de WAN.  <br/> |
   
#### <a name="resiliency-topologies"></a>Topologias de resiliência

A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.
  
**Opções de resiliência do site de filial**

![Opções de resiliência da ramificação de voz](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)
  
#### <a name="survivable-branch-appliance-details"></a>Detalhes do Aparelho de Filial Persistente

O Skype para aparelho de filial persistente Business Server inclui os seguintes componentes:
  
- Um Registrador Avançado para autenticação do usuário, registro e roteamento de chamadas
    
- Um Servidor de Mediação para tratar a sinalização entre o Registrador Avançado e o gateway PSTN
    
- Um gateway PSTN para o roteamento de chamadas para a PSTN como um transporte fallback no caso de uma interrupção da WAN
    
- O SQL Server Express para armazenamento de dados local do usuário
    
O aparelho de filial persistente também inclui troncos PSTN, portas analógicas e um adaptador de Ethernet. 
  
Se a conexão WAN do site de filial para um site central ficar indisponível, os usuários da ramificação interna continuam a ser registrada com o registrador de aparelho de filial persistente e obter o serviço ininterrupto voice usando a conexão de aparelho de filial persistente para o PSTN. Os usuários do site de filial que se conectarem de casa ou de outros locais remotos serão capazes de se registrar em um servidor do Registrador Avançado em um site central quando um link WAN com o site de filial não estiver disponível. Esses usuários contarão com total funcionalidade de comunicações unificadas, sendo a única exceção as chamadas de entrada para o site de filial, que irão para a caixa postal. Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deverá ser restabelecida para os usuários do site de filial. Nem o failover para o aparelho de filial persistente nem a restauração do serviço requer a presença de um administrador de TI.
  
Skype para Business Server suporta até dois aparelho de filial persistente em um site de filial. 
  
#### <a name="survivable-branch-appliance-deployment-overview"></a>Visão geral da implantação do aparelho de filial persistente

O aparelho de filial persistente é fabricado pela fabricantes originais dos equipamentos em parceria com a Microsoft e implantado em nome por revendedores de valor agregados. Essa implantação deve ocorrer somente após Skype para Business Server foi implantado no site central, uma conexão WAN para o site de filial está em vigor e usuários do site de filial estão habilitados para o Enterprise Voice.
  
Para obter detalhes sobre essas fases, consulte [Implantando um servidor ou aparelho de filial persistente](http://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) na documentação de implantação.
  
|**Fase**|**Etapas**|**Direitos de usuário**|
|:-----|:-----|:-----|
|Configurar serviços de domínio do Active Directory para o aparelho de filial persistente  <br/> |**No site central:** <br/>  Crie uma conta de usuário de domínio (ou a identidade corporativa) para o técnico que for instalar e ativar o aparelho de filial persistente no site da filial. <br/>  Crie uma conta de computador (com o nome de domínio totalmente qualificado aplicável (FQDN)) para o aparelho de filial persistente nos serviços de domínio Active Directory. <br/>  No construtor de topologia, crie e publique o aparelho de filial persistente. <br/> |A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians. O aparelho de filial deve pertencer ao grupo RTCSBAUniversalServices, que ocorre automaticamente quando você usa o construtor de topologias.  <br/> |
|Instalar e ativar o aparelho de filial persistente.  <br/> |**No site de filial:** <br/>  Conecte o aparelho de filial persistente para uma porta Ethernet e porta da PSTN. <br/>  Inicie o aparelho de filial persistente. <br/>  Conectar o aparelho de filial para o domínio, usando a conta de usuário de domínio criada para o aparelho de filial persistente no site central. Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador. <br/>  Configure o aparelho de filial persistente, usando a interface de usuário OEM. <br/>  Teste a conectividade PSTN. <br/> |A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians.  <br/> |
   
#### <a name="survivable-branch-server-details"></a>Detalhes do Servidor de Filial Persistente

No construtor de topologia é criar o site de filial, adicione o servidor de filial persistente ao site e execute o Skype para o Assistente de implantação do Business Server no computador onde você deseja instalar a função.
  
### <a name="branch-site-resiliency-requirements"></a>Requisitos de resiliência do site da filial

Este tópico ajudará você a preparar os usuários para resiliência do site de filial e persistência da caixa postal. Ele também especifica os requisitos importantes de hardware e software.
  
#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparação de usuários da filial para resiliência do site de filial

Prepare os usuários para resiliência em filiais, definindo o pool de registradores deles como o aparelho de filial persistente (SBA) ou o servidor de filial persistente.
  
#### <a name="registrar-assignments-for-branch-users"></a>Atribuições do Registrador Avançado para usuários da filial

Independentemente da solução de resiliência de site de filial escolhida, será necessário atribuir um Registrador Avançado primário a cada usuário. Os usuários do site de filial sempre devem registrar com o registrador no site da filial, independentemente se esse registrador reside no aparelho de filial persistente, servidor de filial persistente ou Skype autônoma para Business Server Standard ou Enterprise Edition servidor. Um registro DNS (Sistema de Nomes de Domínio) de recurso de serviços (SRV) é necessário para que o cliente possa descobrir o seu pool de Registradores Avançados. Se o aparelho de filial persistente ficar indisponível, isso é como clientes de site de filial detecta automaticamente o registrador de backup.
  
Se um site de filial não tiver um servidor DNS, existem duas formas alternativas para configurar a descoberta do aparelho de filial persistente ou servidor de filial persistente:
  
- Configure a opção 120 do DHCP no servidor de Dynamic Host Configuration Protocol (DHCP) do site de filial para apontar para o nome de domínio totalmente qualificado (FQDN) do aparelho de filial persistente ou servidor de filial persistente.
    
- Configure o aparelho de filial persistente ou servidor de filial persistente para responder a consultas do DHCP 120.
    
#### <a name="voice-routing-for-branch-users"></a>Roteamento de voz para usuários de filial

É recomendável criar uma política VoIP separada em nível de usuário para os usuários de um site de filial. Essa diretiva deve incluir a uma rota principal que usa o servidor gateway do aparelho de filial persistente ou uma filial e um ou mais rotas de backup que usam um tronco com um gateway PSTN (rede) telefônica comutada pública no site central. Se a rota principal não estiver disponível, a rota de backup que usa um ou mais gateways do site central será utilizada. Dessa forma, independentemente de onde um usuário está registrado — no site da filial registrador ou no pool de registrador de backup no site central — política de VoIP do usuário sempre está em vigor. Essa é uma consideração importante para cenários de failover. Por exemplo, se for necessário renomear o aparelho de filial persistente ou reconfigurar o aparelho de filial persistente para se conectar a um pool de registradores no site central de backup, você deve mover os usuários do site de filial para o site central enquanto durar. (Para obter detalhes sobre como renomear ou reconfigurando um aparelho de filial persistente, consulte [Appendix b: Gerenciando um aparelho de filial persistente](http://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) na documentação de implantação). Se esses usuários não têm políticas em nível de usuário VoIP ou planos de discagem de nível do usuário, quando os usuários são movidos para outro site, as políticas de VoIP do nível do site e discagem de nível de site os planos do site central se aplicam aos usuários, por padrão, em vez do site da filial nível do site VoIP planos políticas e discagem. Nesse cenário, a menos que as políticas VoIP e os planos de discagem em nível de site usados pelo pool de Registradores Avançados de backup também possam ser aplicados aos usuários do site de filial, suas chamadas falharão. Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmond, um plano de discagem com regras de normalização que acrescentem o prefixo +1425 a todas as chamadas de 7 dígitos provavelmente não converterá as chamadas de forma apropriada para esses usuários.
  
> [!IMPORTANT]
> Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de uso do telefone PSTN à política do usuário do escritório da filial e atribuir rotas separadas a cada um deles. A primeira linha ou primário, rota seria direcionar chamadas para o gateway associados com o aparelho de filial persistente (SBA) ou o servidor de ramificação; o segundo ou backup, rota seria direcionar chamadas ao gateway no site central. Ao direcionar as chamadas, o SBA ou o servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso PSTN, antes de tentar o segundo registro. 
  
Para ajudar a garantir que as chamadas de entrada aos usuários do site de filial atingirá esses usuários quando o gateway de filial ou o componente do Windows do site do aparelho de filial persistente está indisponível (que ocorreria, por exemplo, se o aparelho de filial persistente ou uma filial Gateway estiverem fora do ar para manutenção), criar uma rota de failover no gateway (ou trabalhar com seu provedor de Direct Inward Dialing (DID)) para redirecionar chamadas recebidas para o pool de registradores de backup no site central. A partir desse local, as chamadas serão encaminhadas através do link WAN para os usuários da filial. Certifique-se de que a rota converte números concordem com o gateway PSTN ou formatos de número de telefone aceitos do outro ponto tronco. Para obter detalhes sobre como criar uma rota de failover, consulte [Configurando uma rota de Failover](http://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Além disso, crie planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial a fim de normalizar as chamadas de entrada. Se você tiver dois aparelhos de filial persistente em um site de filial, você pode criar um plano de discagem de nível de site para ambas as situações, a menos que um plano de nível de serviço separado para cada é necessário.
  
> [!NOTE]
> Para contabilizar o consumo de recursos do site central pelos usuários de um site de filial que dependam do site central para fins de presença, conferência ou failover, é recomendável considerar cada usuário do site de filial como se estivesse registrado no site central. No momento, não há nenhum limite no número de usuários do site de filial, incluindo usuários registrados com um aparelho de filial persistente. 
  
Também é recomendável criar um plano de discagem e uma política de voz em nível de usuário, e atribuí-los aos usuários do site de filial. Para obter detalhes, consulte [criar ou modificar um plano de discagem no Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md) e [criar a política de roteamento do VoIP para usuários de filiais](http://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) na documentação de implantação.
  
#### <a name="routing-extension-numbers"></a>Roteamento de números de ramal

Ao preparar planos de discagem e políticas de voz para usuários do site de filial, certifique-se de incluir as regras de normalização e regras de conversão que coincidem com as cadeias de caracteres e o formato de número usado em msRTCSIP-line (ou URI da linha) de atributo, para que o Skype para chamadas comerciais habilitado entre os usuários do site de filial e o site central usuários serão roteados corretamente — particularmente quando chamadas devem ser roteadas pela PSTN porque o link de WAN não está disponível. Além disso, há considerações especiais para números discados que contêm números de ramal, e não apenas números de telefone.
  
As regras de normalização e de conversão que fazem a correspondência das URIs de Linha que contêm um número de ramal, exclusivamente ou além de um número de telefone E.164 completo, têm requisitos adicionais. Esta seção descreve vários cenários de exemplo para encaminhar chamadas para URIs de Linha com um número de ramal.
  
Se sua organização não tiver os números de telefone de discagem DID (direta) configurados para usuários individuais e o URI de linha de cada usuário é configurado com apenas um número de ramal, os usuários internos podem chamar um outro discando apenas um número de ramal. No entanto, é necessário configurar regras de normalização aplicáveis às chamadas de um usuário do site de filial para outro do site central, que façam a correspondência dos números de ramal.
  
Em um cenário em que o link WAN entre um site de filial e um site central esteja disponível, as chamadas de usuários do site de filial para os do site central não exigirão que a regra de normalização de correspondência converta o número porque a chamada não é encaminhada através da PSTN. Por exemplo:
  
|**Nome da regra**|**Descrição**|**Padrão de número**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Não converte números de 5 dígitos  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 não é convertido  <br/> |
   
Você também deve acomodar números de ramal para cenários específicos, como, por exemplo, quando o link WAN entre um site de filial e o site central não está disponível, e uma chamada de um site de filial deve ser encaminhada através da PSTN. Durante uma interrupção da WAN, se um usuário do site de filial responde a um usuário do site central discando o site central ramal do usuário, você deve ter uma regra de conversão de saída que adiciona o número de telefone completo do usuário local central. Se o URI de linha de um usuário contém o número de telefone completo da sua organização e o número de ramal único do usuário, em vez de um número de telefone completo que seja exclusivo para o usuário, em seguida, você deve ter uma regra de conversão de saída que adiciona o número de telefone completo da sua organização em vez disso . Por exemplo:
  
|**Descrição**|**Padrão de correspondência**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Converte números de 5 dígitos para o número de telefone e extensão de um usuário  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 é convertido em +14255550123;ext=10001  <br/> |
|Converte números de 5 dígitos para o número de telefone da sua organização e a extensão de um usuário  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 é convertido em +14255550100;ext=10001  <br/> |
   
Neste cenário, se o par do tronco que trata do reencaminhamento para a PSTN não aceitar números de ramal, a regra de conversão de saída também deverá remover o número do ramal. Por exemplo:
  
|**Descrição**|**Padrão de correspondência**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Remove o ramal dos números de telefone com ramais  <br/> |^\+(\d\*); $ ext=(\d\*)  <br/> |+$1  <br/> |+14255550123;ext=10001 é convertido em +14255550123  <br/> |
   
Se é ou não um link WAN disponível, se sua organização não tiver tenha números configurados para usuários individuais e o URI de linha para um usuário contém o número de telefone da sua organização e o número de ramal único do usuário, então você deve configurar seu número linha telefônica da organização URI com um número que seja acessível pelo ponto de tronco ou gateway PSTN no site da filial. Você também deve configurar o URI para incluir seu próprio ramal único para as chamadas sejam roteadas para esse número de linha de número de telefone da sua organização.
  
#### <a name="preparing-for-voice-mail-survivability"></a>Preparação para persistência da caixa postal

Geralmente, o Exchange Unified Messaging (UM) é instalado apenas em um site central e não em sites de filiais. Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo que o link WAN entre o site de filial e o central não esteja disponível. Como resultado, configurar o URI de linha para o número de telefone de UM atendedor automático do Exchange que fornece a caixa postal para usuários do site de filial requer considerações especiais sobre a política de voz, além de plano de discagem e regras de normalização aplicáveis a essa caixa postal número.
  
Aparelhos de filial persistente (SBAs) e servidores de filial persistente fornecem persistência da caixa postal para usuários de filiais durante uma interrupção da WAN. Especificamente, se você estiver usando um aparelho de filial persistente ou servidor de filial persistente e WAN ficar indisponível, o servidor de filial persistente ou SBA redireciona as chamadas não atendidas sobre o PSTN para UM do Exchange no site central. Com um servidor de filial persistente ou SBA, os usuários também podem recuperar mensagens de voz através da PSTN durante uma interrupção da WAN. Finalmente, durante uma interrupção da WAN o aparelho de filial persistente ou servidor de filial persistente enfileira as notificações de chamadas perdidas e as carrega no servidor UM do Exchange quando WAN for restaurada. Para ajudar a garantir que o redirecionamento de correio de voz é resiliente, certifique-se de que você adicione uma entrada para o FQDN do pool site central e uma entrada para o FQDN do servidor de borda ao arquivo hosts no servidor de filial persistente. Caso contrário, o tempo limite da resolução DNS poderá expirar se não houver um servidor DNS no site de filial.
  
Recomendamos definir as configurações a seguir para a persistência da caixa postal dos usuários do site de filial: 
  
- Um administrador do Microsoft Exchange deve configurar o Exchange UM AA (atendedor automático) para aceitar apenas mensagens. Essa configuração desabilita todas as outras funcionalidades genéricas, como a transferência para um usuário ou a transferência para um operador, e limita o AA a aceitar apenas mensagens. Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado a fim de encaminhar a chamada para um operador.
    
- O Skype para o administrador do servidor de negócios deve levar o número de telefone do AA e use esse número de telefone como o número do **exchange um atendedor automático** nas configurações para o aparelho de filial persistente ou servidor de ramificação de redirecionamento da caixa postal.
    
- O Skype para o administrador do servidor de negócios deve usar o UM do Exchange do assinante ao número de telefone de acesso e usar esse número como o número de **acesso do assinante** nas configurações para o aparelho de filial persistente ou servidor de filial persistente de redirecionamento da caixa postal .
    
- O Skype para o administrador do servidor de negócios deve configurar o UM do Exchange para que apenas um plano de discagem seja associado a todos os usuários da filial que precisam acessar a caixa postal durante uma interrupção da WAN.
    
- Quando o link de WAN não estiver disponível, as chamadas para usuários do site de filial pode ser roteado para a caixa de correio de voz de Exchange Unified Messaging (UM) do usuário, mas somente se a política de voz é aplicado à chamada especifica um número de telefone de correio de voz que seja exclusivo e não inclui uma extensão número.
    
#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware e software para resiliência de sites de filial

Os requisitos de hardware e software variam, dependendo da solução de resiliência.
  
#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para Aparelhos de Filial Persistente

Requisitos de hardware e software é incorporada ao aparelho de filial persistente. No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter os endereços IP de clientes; caso contrário, quando a concessão de DHCP expirar, os clientes não terão conectividade IP.
  
Se os servidores DNS do enterprise estiverem localizados somente em sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma interrupção da WAN e, portanto, falhará Skype para descoberta Business Server que usa o DNS SRV (registro de recurso do serviço (SRV)). Para garantir o redirecionamento prompt durante uma interrupção da WAN, registros DNS devem ser armazenado em cache no site da filial. Se o roteador da filial lhe fornecer apoio, ative o cache do DNS. Ou então, você pode implantar um servidor DNS na ramificação. Isso pode ser um servidor autônomo ou uma versão do aparelho de filial persistente que ofereça suporte a recursos DNS. Para obter detalhes, contate o provedor de aparelho de filial persistente.
  
> [!NOTE]
> Não é necessário ter um controlador de domínio em um site de filial. O aparelho de filial persistente autentica clientes usando um certificado especial que ele envia ao cliente em resposta à solicitação de certificado do cliente quando ele entra no. 
  
Skype para clientes de negócios pode descobrir o Skype para Business Server usando a opção 120 do DHCP (opção SIP do registrador). Essa opção pode ser configurada de uma de destas duas maneiras:
  
- Configure o servidor DHCP no site da filial para responder a consultas do DHCP 120, que retornam o FQDN do registrador no aparelho de filial persistente ou servidor de filial persistente.
    
- Ative Skype para negócios servidor DHCP. Quando isso é ativado, o Skype para negócios servidor registrador responde a consultas da opção 120 do DHCP. Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente das Opções 120 do DHCP.
    
Além disso, para sites de filial maiores, com várias sub-redes, agentes de retransmissão DHCP devem ser habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).
  
Finalmente, usuários do site de filial devem ser configurados para Enterprise Voice e provisionados com um ponto de extremidade de comunicações unificadas apropriado.
  
#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para Servidores de Filial Persistente

Os requisitos para servidores de filial persistente são iguais os requisitos para um servidor Front-End. Para obter detalhes, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos do Skype de larga escala para implantações de filiais de servidor de negócios

Para obter detalhes, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) na documentação de planejamento.
  
### <a name="example-configuring-a-failover-route"></a>Exemplo: configurando uma rota de failover

 O exemplo abaixo mostra como um administrador pode definir uma rota de failover para utilizar se o Dallas-GW1 for desativado para manutenção ou estiver indisponível por qualquer outro motivo. As seguintes tabelas ilustram a alteração de configuração necessária.
  
**Tabela 1. Política de usuário**

|**Política de usuário**|**Uso do telefone**|
|:-----|:-----|
|Política de Chamada Padrão  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Política Local de Redmond  <br/> |RedmondLocal  <br/> |
|Política de Chamada de Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |
   
**Tabela 2. Rotas**

|**Nome da rota**|**Padrão de número**|**Uso do telefone**|**Tronco**|**Gateway**|
|:-----|:-----|:-----|:-----|:-----|
|Rota Local de Redmond  <br/> |^\+1 (425|206|253)(\d{7})$  <br/> |Local  <br/> RedmondLocal  <br/> |Trunk1  <br/> Trunk2  <br/> |Red-GW1  <br/> Red-GW2  <br/> |
|Rota Local de Dallas  <br/> |^\+1 (972|214|469)(\d{7})$  <br/> |Local  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |
|Rota Universal  <br/> |^\+?(\d\*)$  <br/> |GlobalPSTNHopoff  <br/> |Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> |Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
|Rota de Usuários de Dallas  <br/> |^\+?(\d\*)$  <br/> |DallasUsers  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |
   
Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.
  

