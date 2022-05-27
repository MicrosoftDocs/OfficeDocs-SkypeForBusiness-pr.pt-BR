---
title: Planejar a Enterprise Voice resiliência no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Saiba como dar suporte à resiliência de voz Skype for Business Server Enterprise Voice sites centrais e sites de filial. As opções de site de filial incluem a implantação de Aparelhos de Filial Persistentes ou Servidores de Filial Persistentes.
ms.openlocfilehash: 493f599f7fbec2a67efaaf59851fd7c2f3b2d144
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675473"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planejar a Enterprise Voice resiliência no Skype for Business Server

Saiba como dar suporte à resiliência de voz Skype for Business Server Enterprise Voice sites centrais e sites de filial. As opções de site de filial incluem a implantação de Aparelhos de Filial Persistentes ou Servidores de Filial Persistentes.

A resiliência de voz refere-se à capacidade dos usuários de continuar a fazer e receber chamadas se um site central que hospeda Skype for Business Server ficar indisponível, seja por uma falha de WAN (rede de longa distância) ou por outra causa. Se um site central falhar, Enterprise Voice serviço deverá continuar ininterrupto por meio do failover contínuo para um site de backup. Em caso de falha de WAN, as chamadas de site de filial devem ser redirecionadas para um gateway PSTN local. Esta seção discute o planejamento de resiliência de voz em caso de falha de WAN ou de site central.

## <a name="central-site-resiliency"></a>Resiliência do site central

Cada vez mais, as empresas têm vários sites espalhados pelo mundo. Manter os serviços de emergência, o acesso ao suporte ajuda e a capacidade de realizar tarefas comerciais críticas quando um site central está fora de serviço é essencial para qualquer Enterprise Voice de resiliência. Quando um site central fica indisponível, as seguintes condições devem ser atendidas:

- O failover de voz deve ser fornecido.

- Os usuários que normalmente se registram com o pool de Front-Ends no site central devem ser capazes de se registrar com um pool de Front-Ends alternativo. Isso pode ser feito criando vários registros SRV dns, cada um deles resolvido para um pool de Diretores ou um pool de Front-Ends em cada um dos seus sites centrais. Você pode ajustar a prioridade e os pesos dos registros SRV para que os usuários atendidos por esse site central obtenham o Diretor e o pool de Front-Ends correspondentes antes daqueles em outros registros SRV.

- As chamadas de e para usuários localizados em outros sites devem ser redirecionadas para o PSTN.

Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.

### <a name="architecture-and-topology"></a>Arquitetura e topologia

Planejar a resiliência de voz em um site central requer uma compreensão básica da função central desempenhada pelo registrador Skype for Business Server na habilitação do failover de voz. O Skype for Business Server Registrador é um serviço que habilita o registro e a autenticação do cliente e fornece serviços de roteamento. Ele é executado em todos os Edição Standard, Servidor Front-End, Diretor ou Aparelho de Filial Persistente. Um pool de Registradores consiste em Serviços de Registrador em execução no pool de Front-Ends e que residem no mesmo site. Um Skype for Business cliente descobre o pool de Front-Ends por meio do seguinte mecanismo de descoberta:

1. Registro SRV de DNS

2. Serviço Web de Descoberta Automática

3. Opção DHCP 120

Depois que Skype for Business cliente se conecta ao pool de Front-Ends, ele é direcionado pelo balanceador de carga para um dos Servidores Front-End no pool. Esse Servidor Front-End, por sua vez, redireciona o cliente para um Registrador preferencial no pool.

Cada usuário habilitado para Enterprise Voice é atribuído a um pool de Registradores específico, que se torna o pool de Registradores primário desse usuário. Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de Registradores primário. Para considerar o consumo de recursos do site central por qualquer usuário do site de filial que dependa do site central para presença, conferência ou failover, recomendamos que você considere cada usuário do site de filial como se o usuário fosse um usuário registrado no site central. Atualmente, não há limites para o número de usuários do site de filial, incluindo usuários registrados com um Aparelho de Filial Persistente.

Para garantir a resiliência de voz em caso de falha de site central, o pool de Registradores primário deve ter um único pool de Registradores de backup designado localizado em outro site. O backup pode ser configurado usando as configurações de resiliência do Construtor de Topologias. Supondo um link wan resiliente entre os dois sites, os usuários cujo pool de Registradores primário não está mais disponível são direcionados automaticamente para o pool de Registradores de backup.

As etapas a seguir descrevem o processo de descoberta e registro do cliente:

1. Um cliente descobre Skype for Business Server por meio de registros SRV dns. No Skype for Business Server, os registros SRV dns podem ser configurados para retornar mais de um FQDN para a consulta SRV dns. Por exemplo, se a Empresa Contoso tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de Diretores em cada site central, os registros SRV dns poderão apontar para os FQDNs do pool de diretores em cada um dos três locais. Desde que o pool de Diretores em um dos locais esteja disponível, o cliente pode se conectar ao primeiro salto Skype for Business Server.

    > [!NOTE]
    > Usar um pool de Diretores é opcional. Um pool de Front-Ends pode ser usado em vez disso.

2. O pool de diretores informa ao Skype for Business cliente sobre o pool de Registradores primário do usuário e o pool de Registradores de backup.

3. O Skype for Business cliente tenta se conectar ao pool de Registradores primário do usuário primeiro. Se o pool de Registradores primário estiver disponível, o Registrador aceitará o registro. Se o pool de Registradores primário não estiver disponível, Skype for Business cliente tentará se conectar ao pool de Registradores de backup. Se o pool de Registradores de backup estiver disponível e tiver determinado que o pool de Registradores primário do usuário não está disponível (detectando a falta de pulsação para um intervalo de failover especificado), o pool de Registradores de backup aceitará o registro do usuário. Depois que o Registrador de backup detectar que o Registrador primário está novamente disponível, o pool de Registradores de backup redirecionará os clientes de failover para o pool primário.

### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Os seguintes requisitos e recomendações para implementar a resiliência de voz do site central são apropriados para a maioria das organizações:

- Os sites nos quais residem os pools de Registradores primário e de backup devem ser conectados por um link WAN resiliente.

- Cada site central deve conter um pool de Registradores que consiste em um ou mais Registradores.

- Cada pool de Registradores deve ter balanceamento de carga usando balanceamento de carga DNS, balanceamento de carga de hardware ou ambos. Para obter informações detalhadas sobre como planejar sua configuração de balanceamento de carga, consulte [os requisitos de balanceamento de carga para Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).

- Cada usuário deve ser atribuído a um pool de Registradores primário usando o cmdlet Skype for Business Server Management Shell **set-CsUser** ou o Skype for Business Server Painel de Controle.

- O pool de Registradores primário deve ter um único pool de Registradores de backup localizado em um site central diferente.

- O pool de Registradores primário deve ser configurado para fazer failover para o pool de Registradores de backup. Por padrão, o Registrador primário é definido para fazer failover para o pool de Registradores de backup após um intervalo de 300 segundos. Você pode alterar esse intervalo usando o Skype for Business Server Construtor de Topologias.

- Configurar uma rota de failover. Ao configurar a rota, especifique um gateway localizado em um site diferente do gateway especificado na rota primária.

- Se o site central contiver seu servidor de gerenciamento primário e o site provavelmente ficar inativo por um longo período, você precisará reinstalar suas ferramentas de gerenciamento no site de backup; caso contrário, você não poderá alterar as configurações de gerenciamento.

### <a name="dependencies"></a>Dependências

Skype for Business Server depende dos seguintes componentes de infraestrutura e software para garantir a resiliência de voz:

|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolução de registros SRV e registros A para conectividade servidor-servidor e cliente-servidor  <br/> |
|Exchange e Exchange Web (EWS)  <br/> |Armazenamento de contatos; dados do calendário  <br/> |
|Exchange Unificação de Mensagens e serviços Exchange Web  <br/> |Logs de chamadas, lista de caixa postal, caixa postal  <br/> |
|Opções de DHCP 120  <br/> |Se o DNS SRV não estiver disponível, o cliente tentará usar a Opção 120 do DHCP para descobrir o Registrador. Para que isso funcione, um servidor DHCP deve ser configurado ou Skype for Business Server DHCP deve ser habilitado.  <br/> |

### <a name="survivable-voice-features"></a>Recursos de voz ressuciáveis

Se os requisitos e recomendações anteriores tiverem sido implementados, os seguintes recursos de voz serão fornecidos pelo pool de Registradores de backup:

- Chamadas PSTN de saída

- Chamadas PSTN de entrada, se o provedor de serviços de telefonia der suporte à capacidade de fazer failover para um site de backup

- Enterprise chamadas entre usuários no mesmo site e entre dois sites diferentes

- Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

- Mensagens instantâneas de duas partes e compartilhamento de áudio e vídeo entre usuários no mesmo site

- Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamadas e serviços de chamada de equipe, mas somente se ambas as partes para chamar delegação, ou todos os membros da equipe, forem configuradas no mesmo site.

- Os telefones e clientes existentes continuam funcionando.

- CDR (registro de detalhes das chamadas)

- Autenticação e autorização

Dependendo de como eles são configurados, os seguintes recursos de voz podem ou não funcionar quando um site central primário está fora de serviço:

- Depósito e recuperação de caixa postal

    Se você quiser disponibilizar Exchange UM quando o site central primário estiver fora de serviço, siga um dos seguintes procedimentos:

  - Altere os registros SRV dns para que os Exchange um no site central apontem para fazer backup Exchange servidores de UNIFICAÇÃO em outro site.

  - Configure o plano de discagem da UNIFICAção Exchange de cada usuário para incluir servidores um do Exchange no site central e no site de backup, mas designe o backup Exchange um servidores como desabilitados. Se o site primário ficar indisponível, o Exchange administrador terá que marcar os Exchange um no site de backup como habilitados.

    Se nenhuma das soluções anteriores for possível, Exchange UM não estará disponível no caso de o site central ficar indisponível.

- Conferência de todos os tipos

    Um usuário que fez failover em um site de backup pode ingressar em uma conferência criada ou hospedada por um organizador cujo pool está disponível, mas não pode criar ou hospedar uma conferência em seu próprio pool primário, que não está mais disponível. Da mesma forma, outros usuários não podem ingressar em conferências hospedadas no pool primário do usuário afetado.

Os seguintes recursos de voz não funcionam quando um site central primário está fora de serviço:

- Atendedor Automático de Conferência

- Roteamento baseado em presença e DND

- Atualizando configurações de encaminhamento de chamadas

- Serviço de Grupo de Resposta e Estacionamento de Chamada

- Provisionando novos telefones e clientes

- Pesquisa na Web do Catálogo de Endereços

## <a name="branch-site-resiliency"></a>Resiliência do site de filial

Se você quiser fornecer resiliência de site de filial, ou seja, serviço de Enterprise Voice de alta disponibilidade, você tem três opções para fazer isso:

- Aplicativo de Filial Persistente

- Survivable Branch Server

- Uma implantação Skype for Business Server completa no site de filial

Este guia ajudará você a avaliar qual solução de resiliência é melhor para a organização e, com base em sua solução de resiliência, a solução de conectividade PSTN a ser usada. Ele também o ajuda a se preparar para implantar a solução escolhida, descrevendo os pré-requisitos e outras considerações de planejamento.

### <a name="branch-site-resiliency-features"></a>Recursos de resiliência do site de filial

Se você fornecer resiliência de site de filial, se a conexão WAN de um site de filial a um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz deverão continuar disponíveis:

- Chamadas PSTN (rede telefônica pública comunada) de entrada e saída

- Enterprise chamadas entre usuários no mesmo site e entre dois sites diferentes

- Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

- Mensagens instantâneas de duas partes

- Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamadas e serviços de chamada de equipe, mas somente se o representante e o representante (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe, forem configurados no mesmo site

- Registros de detalhes da chamada (CDRs)

- Conferência de discagem PSTN com Atendedor Automático de Conferência

- Recursos de caixa postal, se você definir as configurações de redirecionamento de caixa postal.

- Autenticação e autorização de usuário

Os seguintes recursos estarão disponíveis somente se sua solução de resiliência for uma implantação de Skype for Business Server em escala completa no site de filial:

- Conferência de mensagens instantâneas, Web e A/V

- Roteamento baseado em Presença e Não Incomodar (DND) (em que as chamadas são impedidas de tocar em extensões que têm o DND ativado)

- Atualizando configurações de encaminhamento de chamadas

- Aplicativo grupo de resposta e aplicativo estacionamento de chamada

- Provisionando novos telefones e clientes, mas somente se Active Directory Domain Services estiver presente no site da filial.

- Avançado 9-1-1 (E9-1-1)

    Se o E9-1-1 for implantado e o tronco SIP no local central não estiver disponível porque o link wan está inativo, o Aparelho de Filial Persistente encaminhará chamadas E9-1-1 para o gateway de branch local. Para habilitar esse recurso, as políticas de voz dos usuários do site de filial devem rotear chamadas para o gateway local em caso de falha de WAN.

> [!NOTE]
> Não há suporte para SBA (filial existente) para XMPP. Os usuários hospedados em uma configuração do SBA não poderão enviar mensagens instantâneas ou ver a Presença com contatos XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluções de resiliência de site de filial

Há vantagens óbvias em fornecer resiliência de site de filial para sua organização. Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão a ter um serviço de Enterprise Voice e caixa postal (se você definir as configurações de redirecionamento de caixa postal). No entanto, para sites com menos de 25 usuários, uma solução de resiliência pode não fornecer um retorno suficiente sobre o investimento.

Se decidir fornecer a resiliência do site de filial, você tem três opções. Use a tabela a seguir para ajudá-lo a determinar qual opção é a melhor para sua organização.

|**Se você...**|**Recomendamos que você use um...**|
|:-----|:-----|
|Hospede entre 25 e 1.000 usuários no seu site de filial se o retorno sobre o investimento não suportar uma implantação completa ou em um local em que o suporte administrativo não estiver disponível  <br/> |Aplicativo de Filial Persistente  <br/> O Aparelho de Filial Persistente é um servidor de folha padrão do setor com um Registrador Skype for Business Server e Servidor de Mediação em execução no Windows Server 2008 R2. O Aparelho de Filial Persistente também contém um gateway PSTN (rede telefônica pública comucionável). Dispositivos qualificados de terceiros (desenvolvidos pelos parceiros da Microsoft no programa de qualificação/certificação SBA [aparelho de filial persistente]) fornece uma conexão PSTN contínua caso uma WAN falhe, mas essa abordagem não fornece a presença e a conferência resilientes porque esses recursos dependem do servidores Front-End no site central.  <br/> Para obter detalhes sobre Aparelhos de Filial Persistentes, consulte "Detalhes do Aparelho de Filial Persistente", mais adiante neste tópico.  <br/> **Nota:** Se você decidir também usar um tronco SIP com seu Aparelho de Filial Persistente, entre em contato com o fornecedor do Aparelho de Filial Persistente para saber qual provedor de serviços é melhor para sua organização. <br/> |
|Hospedar entre 1.000 e 2.000 usuários em seu site de filial, não tem uma conexão WAN resiliente e treinou Skype for Business Server administradores disponíveis  <br/> |Servidor de Filial Persistente ou dois Aparelhos de Filial Persistentes.  <br/> O Servidor de Filial Existente é uma Windows Server que tem requisitos de hardware especificados que Skype for Business Server software do Registrador e do Servidor de Mediação instalados nele. Ele deve ser conectado a um gateway PSTN ou a um tronco SIP a um provedor de serviço telefônico.  <br/> Para obter detalhes sobre servidores de ramificação existentes, consulte "Detalhes do servidor de filial existente", mais adiante neste tópico.  <br/> |
|Se você precisar de recursos de presença e conferência, além de recursos de voz para até 5.000 usuários e tiver treinado Skype for Business Server administradores disponíveis  <br/> |Implante como um site central com um servidor Standard Edition e não como um site de filial.  <br/> Uma implantação de Skype for Business Server de escala completa fornece uma conexão PSTN contínua e presença e conferência resilientes em caso de falha de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologia de resiliência

A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.

**Opções de resiliência do site de filial**

![Opções de resiliência de branch de voz.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalhes do aparelho de filial persistente

O Skype for Business Server aparelho de filial persistente inclui os seguintes componentes:

- Um Registrador para a autenticação do usuário, registro e roteamento de chamada

- Um Servidor de Mediação para a manipulação de sinalização entre o Registrador e o gateway PSTN

- Um gateway PSTN para o roteamento de chamadas ao PSTN como um transporte fallback no caso de uma interrupção da WAN

- SQL Server Express para armazenamento de dados do usuário local

O Aparelho de Filial Persistente também inclui troncos PSTN, portas analógicas e um adaptador Ethernet.

Se a conexão WAN do site de filial a um site central ficar indisponível, os usuários do branch interno continuarão a ser registrados com o Registrador de Aparelhos de Filial Persistente e obterão o serviço de voz ininterrupto usando a conexão do Aparelho de Filial Persistente com o PSTN. Os usuários do site de filial que se conectam de casa ou de outro locais remotos serão capazes de se registrar com um servidor Registrador em um site central quando um link de WAN ao site de filial estiver indisponível. Esses usuários terão a funcionalidade de comunicações completamente unificadas com única exceção de que as chamadas de entrada ao site de filial irão para a caixa postal. Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deve ser restabelecida aos usuários do site de filial. Nem o failover para o Aparelho de Filial Persistente nem a restauração do serviço exigem a presença de um administrador de TI.

Skype for Business Server dá suporte a até dois Aparelhos de Filial Persistentes em um site de filial.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Visão geral de implantação de aparelho de filial persistente

O Aparelho de Filial Persistente é fabricado por fabricantes de equipamentos originais em parceria com a Microsoft e implantado em seu nome por varejistas de valor agregado. Essa implantação deve ocorrer somente depois Skype for Business Server implantação no site central, uma conexão WAN com o site de filial está em vigor e os usuários do site de filial estão habilitados para Enterprise Voice.

Para obter detalhes sobre essas fases, consulte [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) na documentação de Implantação.

|**Fase**|**Etapas**|**Direitos do usuário**|
|:-----|:-----|:-----|
|Configurar o Active Directory Domain Services para o Aparelho de Filial Persistente  <br/> |**No site central:** <br/>  Crie uma conta de usuário de domínio (ou identidade corporativa) para o técnico que instalará e ativará o Aparelho de Filial Persistente no site da filial. <br/>  Crie uma conta de computador (com o FQDN (nome de domínio totalmente qualificado) aplicável para o Aparelho de Filial Persistente no Active Directory Domain Services. <br/>  No Construtor de Topologias, crie e publique o Aparelho de Filial Persistente. <br/> |O usuário técnico deve ser um membro do RTCUniversalSBATechnicians. O Aparelho de Filial Persistente deve pertencer ao grupo RTCSBAUniversalServices, que ocorre automaticamente quando você usa o Construtor de Topologias.  <br/> |
|Instale e ative o Aparelho de Filial Persistente.  <br/> |**No site de filial:** <br/>  Conexão aparelho de filial persistente para uma porta Ethernet e uma porta PSTN. <br/>  Inicie o Aparelho de Filial Persistente. <br/>  Ingresse o Aparelho de Filial Persistente no domínio, usando a conta de usuário do domínio criada para o Aparelho de Filial Persistente no site central. Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador. <br/>  Configure o Aparelho de Filial Persistente usando a interface do usuário do OEM. <br/>  Teste a conectividade do PSTN. <br/> |O usuário técnico deve ser um membro do RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalhes do servidor de filial persistente

No Construtor de Topologias, crie o site de filial, adicione o Servidor de Filial Existente a esse site e execute o Assistente de Implantação do Skype for Business Server no computador em que você deseja instalar a função.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resiliência do site de filial

Este tópico ajudará a você preparar usuários para resiliência de site de filial e persistência da caixa postal, e também especifica os requisitos de hardware e software importantes.


#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparação de usuários da filial para resiliência de site de filial

Prepare os usuários para resiliência do site de filial definindo seu pool de Registradores como o SBA (Aparelho de Filial Persistente) ou Servidor de Filial Persistente.

#### <a name="registrar-assignments-for-branch-users"></a>Atribuições do registrador avançado para usuários da filial

Independentemente de qual solução de resiliência de site de filial você escolher, você precisará atribuir um Registrador primário a cada usuário. Os usuários do site de filial sempre devem se registrar no Registrador no site de filial, independentemente de esse Registrador residir no Aparelho de Filial Persistente, no Servidor de Filial Persistente ou no servidor autônomo Skype for Business Server Standard ou Edição Enterprise. Um registro de recurso de serviço (SRV) de sistema de nome de domínio (DNS) é necessário para que o cliente possa descobrir seu pool de Registrador. Se o Aparelho de Filial Persistente ficar indisponível, os clientes do site de filial descobrirão automaticamente o Registrador de backup.

Se um site de filial não tiver um servidor DNS, há duas maneiras alternativas de configurar a descoberta do Aparelho de Filial Persistente ou do Servidor de Filial Persistente:

- Configure a opção DHCP 120 no servidor DHCP (Dynamic Host Configuration Protocol) do site de filial para apontar para o FQDN (nome de domínio totalmente qualificado) do Aparelho de Filial Persistente ou Servidor de Filial Persistente.

- Configure o Aparelho de Filial Persistente ou o Servidor de Filial Persistente para responder a consultas DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Roteamento de voz para usuários de filial

É recomendável criar uma política separada de VoIP (Voice over Internet Protocol ) no nível do usuário para usuários em um site de filial. Essa política deve incluir uma rota primária que usa a Central de Filial Persistente ou gateway de servidor de filial e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comunada) no site central. Se a rota principal estiver indisponível, a rota de backup que usa um ou mais gateways do site central será utilizada. Dessa forma, independentemente de onde um usuário está registrado , no Registrador do site de filial ou no pool de Registradores de backup no site central, a política VoIP do usuário está sempre em vigor. Esta é uma consideração importante para cenários de failover. Por exemplo, se você precisar renomear o Aparelho de Filial Persistente ou reconfigurar o Aparelho de Filial Persistente para se conectar a um pool de Registradores de backup no site central, deverá mover os usuários do site de filial para o site central pela duração. (Para obter detalhes sobre como renomear ou reconfigurar um Aparelho de Filial Persistente, consulte o Apêndice [B:](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) Gerenciando um Aparelho de Filial Persistente na documentação de implantação.) Se esses usuários não tiverem políticas VoIP no nível do usuário ou planos de discagem no nível do usuário, quando os usuários forem movidos para outro site, as políticas VoIP no nível do site e os planos de discagem no nível do site central serão aplicados aos usuários por padrão, em vez das políticas voIP e planos de discagem no nível do site da filial. Neste cenário, a menos que as políticas de VoIP e planos de discagem de nível de site usados pelo pool de registradores de backup também possam ser aplicadas aos usuários do site de filial, suas chamadas falharão. Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmund, um plano de discagem com regras de normalização que precedam +1425 a todas as chamadas de 7 dígitos provavelmente não traduzirá chamadas de forma apropriada para estes usuários.

> [!IMPORTANT]
> Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de utilização de telefone do PSTN à política do usuário do escritório da filial e atribuir rotas separadas para cada uma. A primeira rota, ou primária, direcionaria chamadas para o gateway associado ao SBA (Aparelho de Filial Persistente) ou servidor de filial; a segunda rota, ou backup, direcionaria chamadas para o gateway no site central. Ao direcionar chamadas, o SBA ou servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso do PSTN antes de tentar o segundo registro de uso.

Para ajudar a garantir que as chamadas de entrada para usuários do site de filial cheguem a esses usuários quando o gateway de branch ou o componente Windows do site aparelho de filial persistente não estiver disponível (o que aconteceria, por exemplo, se o Gateway de Filial persistente ou o gateway de filial estivesse inativo para manutenção), crie uma rota de failover no gateway (ou trabalhe com seu provedor de DID (Discagem Direta Interna) para redirecionar chamadas de entrada para o pool do Registrador de backup no site central. Daí, as chamadas serão roteadas sobre o link WAN para os usuários da filial. Certifique-se de que a rota traduz números para estar em conformidade com o gateway PSTN ou outros formatos de número de telefone aceitos pelo par de tronco. Para detalhes sobre a criação de uma rota de failover, consulte [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). Crie também planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial para normalizar chamadas de entrada. Se você tiver dois Aparelhos de Filial Persistentes em um site de filial, poderá criar um plano de discagem no nível do site para ambos, a menos que um plano de nível de serviço separado para cada um seja necessário.

> [!NOTE]
> Para suportar o consumo dos recursos do site central pelos usuários de qualquer site de filial que se apoiem no site central para presença, conferência ou failover, é recomendável considerar cada usuário de site de filial como se estivesse registrado no site central. Atualmente, não há limites para o número de usuários do site de filial, incluindo usuários registrados com um Aparelho de Filial Persistente.

Também é recomendável criar um plano de discagem de nível de usuário e uma política de voz e atribuí-los a usuários do site de filial. Para obter detalhes, consulte Criar ou modificar um plano de discagem [no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) e criar a política de roteamento [voIP](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) para usuários de branch na documentação de implantação.

#### <a name="routing-extension-numbers"></a>Números de extensão de roteamento

Ao preparar planos de discagem e políticas de voz para usuários do site de filial, certifique-se de incluir regras de normalização e regras de conversão que correspondam às cadeias de caracteres e ao formato de número usado no atributo msRTCSIP-line (ou URI de linha), para que as chamadas do Skype for Business habilitadas entre usuários do site de filial e usuários do site central sejam roteadas corretamente, especialmente quando as chamadas devem ser roteadas novamente pelo PSTN porque o link wan não está disponível. Existem considerações especiais adicionais para números discados que contêm números de extensão, em vez de apenas números de telefone.

Regras de normalização e de tradução que correspondam a URIs de Linha que contêm um número de extensão, seja de forma exclusiva ou além de um número de telefone totalmente E.164, possuem requisitos adicionais. Esta seção descreve vários cenários de exemplo para rotear chamadas para URIs de Linha com um número de extensão.

Se sua organização não possui Números Fixos Virtuais (DID) configurados para usuários individuais e a URI de Linha de cada usuário está configurada apenas com um número de extensão, usuários internos podem ligar uns para os outros discando apenas um número de extensão. No entanto, é necessário configurar regras de normalização que possam se aplicar a chamadas a partir de um site de filial para um usuário do site central que correspondam a números de extensão.

Em um cenário onde o link WAN entre um site de filial e um site central esteja disponível, chamadas de usuários do site de filial para usuários do site central não exigem que a regra de normalização correspondente traduza o número porque a chamada não é roteada sobre o PSTN. Por exemplo:

|**Nome da regra**|**Descrição**|**Padrão de número**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Não traduz números de 5 dígitos  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 não é traduzido  <br/> |

Você também deve acomodar números de extensão para cenários específicos, como quando o link WAN entre um site de filial e o site central está indisponível e um chamada de um site de filial deve ser roteada através do PSTN. Durante uma interrupção de WAN, se um usuário do site de filial chamar um usuário do site central apenas discando a extensão do usuário do site central, você deverá ter uma regra de conversão de saída que adicione o número de telefone completo do usuário do site central. Se o URI de linha de um usuário contiver o número de telefone completo da sua organização e o número de extensão exclusivo do usuário em vez de um número de telefone completo exclusivo para o usuário, você deverá ter uma regra de conversão de saída que adicione o número de telefone completo da sua organização. Por exemplo:

|**Descrição**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Converte números de 5 dígitos para o número de telefone e a extensão de um usuário  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 é traduzido como +14255550123;ext=10001  <br/> |
|Converte números de 5 dígitos para o número de telefone da sua organização e a extensão de um usuário  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 é traduzido como +14255550100;ext=10001  <br/> |

Neste cenário, se o ponto do tronco que trata o re-roteamento para o PSTN não suportar os números de extensão, a regra de tradução de saída também deve remover o número de extensão. Por exemplo:

|**Descrição**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Remove a extensão dos números de telefone com extensões  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001 é traduzido como +14255550123  <br/> |

Se um link WAN estiver disponível ou não, se sua organização não tiver números DID configurados para usuários individuais e o URI de Linha de um usuário contiver o número de telefone da sua organização e o número de extensão exclusivo do usuário, você deverá configurar o URI de Linha do número de telefone da sua organização com um número que seja acessível pelo par de tronco ou pelo gateway PSTN no site da filial. Você também deve configurar o URI de Linha do número de telefone da sua organização para incluir sua própria extensão exclusiva para que as chamadas sejam roteados para esse número.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparação para persistência de caixa postal

Exchange Unificação de Mensagens (UM) geralmente é instalada apenas em um site central e não em sites de filial. Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo se o link WAN entre o site da filial e o site central estiver indisponível. Como resultado, a configuração do URI de linha para o número de telefone do Atendedor Automático da UM do Exchange que fornece caixa postal para usuários do site de filial requer considerações especiais, além da política de voz, do plano de discagem e das regras de normalização aplicáveis a esse número de caixa postal.

Os SBAs (Aparelhos de Filial Persistentes) e os Servidores de Filial Persistentes fornecem manutenção de caixa postal para usuários de filial durante uma interrupção wan. Especificamente, se você estiver usando um Aparelho de Filial Persistente ou Um Servidor de Filial Persistente e a WAN ficar indisponível, o SBA ou o Servidor de Filial Persistente redirecionará chamadas não respondidas pelo PSTN para Exchange UM no site central. Com um SBA ou Servidor de Filial Existente, os usuários também podem recuperar mensagens de caixa postal por meio do PSTN durante uma interrupção de WAN. Por fim, durante uma interrupção de WAN, o Aparelho de Filial Persistente ou o Servidor de Filial Persistente enfileira notificações de chamada perdida e, em seguida, carrega-as no servidor de UNIFICAÇÃO Exchange quando a WAN é restaurada. Para ajudar a garantir que o redirecionamento de caixa postal seja resiliente, adicione uma entrada para o FQDN do pool de sites central e uma entrada para o FQDN do Servidor de Borda ao arquivo de hosts no Servidor de Filial Persistente. Do contrário, a resolução do DNS pode ultrapassar o tempo se não houver um servidor DNS no site da filial.

Recomendamos seguir as configurações a seguir para a persistência de caixa postal para usuários de filiais:

- Um administrador do Microsoft Exchange deve configurar Exchange AA (Atendedor Automático de UNIFICAÇÃO) para aceitar apenas mensagens. Esta configuração desabilita todas as outras funcionalidades genéricas, como transferência para um usuário ou transferência para um operador e limita o AA a aceitar apenas mensagens. Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado para rotear a chamada para um operador.

- O Skype for Business Server administrador deve pegar o número de telefone AA e usar esse número de telefone como o número do atendedor automático do **exchange nas** configurações de redirecionamento de caixa postal para o Aparelho de Filial Persistente ou servidor de filial.

- O administrador do Skype for Business Server deve obter o número de telefone de acesso do assinante Exchange UM e usar esse número como o número  de acesso do assinante nas configurações de redirecionamento de caixa postal para o Aparelho de Filial Persistente ou Servidor de Filial Persistente.

- O Skype for Business Server administrador deve configurar Exchange UM para que apenas um plano de discagem seja associado a todos os usuários de filial que precisam de acesso à caixa postal durante uma interrupção wan.

- Quando o link WAN não estiver disponível, as chamadas aos usuários do site de filial poderão ser roteados para a caixa de correio de voz do Exchange UNIFICAÇÃO (UNIFICAÇÃO DE MENSAGENS) do usuário, mas somente se a política de voz aplicada à chamada especificar um número de telefone de caixa postal exclusivo e não incluir um número de extensão.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware e software para resiliência de site de filial

Os requisitos de hardware e software variam, dependendo da sua solução de resiliência.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para Aparelhos de Filial Persistente

O hardware e o software necessários são integrados ao Aparelho de Filial Persistente. No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter endereços IP clientes; do contrário, quando a concessão do DHCP expirar, os clientes não terão conectividade IP.

Se os servidores DNS corporativos estiverem localizados apenas em sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma interrupção de WAN e, portanto Skype for Business Server, uma descoberta que usa o registro de recurso SRV (serviço) dns falhará. Para garantir o re-roteamento imediato durante uma interrupção da WAN, registros DNS devem ser armazenados em cache no site da filial. Se o roteador da filial for compatível, ative o cache do DNS. Ou você pode implantar um servidor DNS na filial. Pode ser um servidor autônomo ou uma versão do Aparelho de Filial Persistente que dá suporte a recursos dns. Para obter detalhes, entre em contato com seu provedor de Aparelho de Filial Persistente.

> [!NOTE]
> Não é necessário ter um controlador de domínio no site da filial. O Aparelho de Filial Persistente autentica clientes usando um certificado especial que envia o cliente em resposta à solicitação de certificado do cliente quando ele entra.

Skype for Business clientes podem descobrir o Skype for Business Server usando a Opção DHCP 120 (Opção registrador SIP). Ela pode ser configurada em uma de duas formas:

- Configure o servidor DHCP no site de filial para responder a consultas DHCP 120, que retornam o FQDN do Registrador no Aparelho de Filial Persistente ou servidor de filial persistente.

- Ative Skype for Business Server DHCP. Quando isso é ativado, o registrador Skype for Business Server responde às consultas da Opção DHCP 120. Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente da Opção 120 do DHCP.

Além disso, para sites de filial maiores, que possuem várias sub-redes, agentes de retransmissão DHCP devem estar habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).

Por fim, os usuários do site de filial devem ser configurados para Enterprise Voice e provisionados com um ponto de extremidade de comunicação unificada apropriado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para Servidores de Filial Persistente

Os requisitos para Servidores de Filial Existentes são os mesmos dos requisitos para um Servidor Front-End. Para obter detalhes, consulte [Requisitos do servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos para Full-Scale Skype for Business Server Branch-Site implantações

Para obter detalhes, [consulte Os requisitos do servidor Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) na documentação planejamento.

### <a name="example-configuring-a-failover-route"></a>Exemplo: configurando uma rota de failover

 O exemplo abaixo mostra como um administrador pode definir uma rota de failover para utilizar se o Dallas-GW1 for desativado para manutenção ou estiver indisponível por qualquer outro motivo. As seguintes tabelas ilustram a alteração de configuração necessária.

**Tabela 1. Política de usuário**

|**Política de usuário**|**Uso do telefone**|
|:-----|:-----|
|Política de Chamada Padrão  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Política Local de Redmond  <br/> |RedmondLocal  <br/> |
|Política de Chamada de Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabela 2. Rotas**


| **Nome da rota**             | **Padrão de número** | **Uso do telefone**         | **Tronco**                                 | **Gateway**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Rota Local de Redmond  <br/> | ^\+1(425           | 206                     | 253)(\d{7})$  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Rota Local de Dallas  <br/>  | ^\+1(972           | 214                     | 469)(\d{7})$  <br/>                       | Local  <br/>                                    |
| Rota Universal  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Tronco1  <br/> Tronco2  <br/> Tronco3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Rota de Usuários de Dallas  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Tronco3  <br/>                             | Dallas-GW1  <br/>                               |

Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.