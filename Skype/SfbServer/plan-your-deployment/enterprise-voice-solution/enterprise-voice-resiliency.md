---
title: Planejar a resiliência do Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Saiba como dar suporte à resiliência de voz no Skype for Business Server Enterprise Voice, em sites centrais e filiais. As opções de site de filial incluem a implantação de Aparelhos de FilialVivíveis ou Servidores de Filial Sobrevivência.
ms.openlocfilehash: d2b3efe36470e11d901b9b298cf955a04dd40766
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825751"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planejar a resiliência do Enterprise Voice no Skype for Business Server

Saiba como dar suporte à resiliência de voz no Skype for Business Server Enterprise Voice, em sites centrais e filiais. As opções de site de filial incluem a implantação de Aparelhos de FilialVivíveis ou Servidores de Filial Sobrevivência.

A resiliência de voz se refere à capacidade dos usuários de continuar a fazer e receber chamadas se um site central que hospeda o Skype for Business Server ficar indisponível, seja por uma falha de rede de área ampla (WAN) ou por outra causa. Se um site central falhar, o serviço do Enterprise Voice deverá continuar sem interrupções por meio de failover contínuo para um site de backup. Em caso de falha da WAN, as chamadas de site de filial devem ser redirecionadas para um gateway PSTN local. Esta seção discute o planejamento de resiliência de voz no caso de falha de WAN ou de site central.

## <a name="central-site-resiliency"></a>Resiliência do site central

Cada vez mais, as empresas têm vários sites espalhados pelo mundo. Manter os serviços de emergência, o acesso ao help desk e a capacidade de realizar tarefas críticas de negócios quando um site central está fora de serviço é essencial para qualquer solução de resiliência do Enterprise Voice. Quando um site central fica indisponível, as seguintes condições devem ser atendidas:

- O failover de voz deve ser fornecido.

- Os usuários que normalmente se registram no pool de Front-End no site central devem ser capazes de se registrar em um pool de Front-End alternativo. Isso pode ser feito criando vários registros SRV DNS, cada um deles resolvido para um pool de Diretores ou pool de Front-End em cada um dos seus sites centrais. Você pode ajustar a prioridade e os pesos dos registros SRV para que os usuários atendidos por esse site central recebam o Diretor e o pool de Front-End correspondentes antes daqueles em outros registros SRV.

- As chamadas de e para usuários localizados em outros sites devem ser redirecionadas para a PSTN.

Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.

### <a name="architecture-and-topology"></a>Arquitetura e topologia

O planejamento da resiliência de voz em um site central requer uma compreensão básica da função central desempenhada pelo Registrador do Skype for Business Server na habilitação do failover de voz. O Registrador do Skype for Business Server é um serviço que habilita o registro e a autenticação do cliente e fornece serviços de roteamento. Ele é executado em todos os servidores Standard Edition, Servidor Front End, Diretor ou Aparelho de FilialVivível. Um pool de Registrador consiste em Serviços do Registrador em execução no pool de Front-End e residindo no mesmo site. Um cliente do Skype for Business descobre o pool de Front-End por meio do seguinte mecanismo de descoberta:

1. Registro SRV de DNS

2. Serviço Web de Descoberta Automática

3. Opção 120 do DHCP

Depois que o cliente do Skype for Business se conecta ao pool de Front-End, ele é direcionado pelo balanceador de carga para um dos Servidores front-end no pool. Esse Servidor Front End, por sua vez, redireciona o cliente para um Registrador preferencial no pool.

Cada usuário habilitado para o Enterprise Voice é atribuído a um determinado pool de Registradores, que se torna o pool de Registradores Registradores primário desse usuário. Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de Registradores Primários. Para levar em conta o consumo de recursos do site central por qualquer usuário do site de filial que dependa do site central para presença, conferência ou failover, recomendamos que você considere cada usuário do site de filial como se fosse um usuário registrado no site central. Atualmente, não há limites para o número de usuários do site de filial, incluindo usuários registrados em um Aparelho de FilialVivível.

Para garantir a resiliência de voz em caso de falha do site central, o pool de Registradores Registradores primário deve ter um único pool de Registrador de backup designado localizado em outro site. O backup pode ser configurado usando as configurações de resiliência do Construtor de Topologias. Supondo um link WAN resiliente entre os dois sites, os usuários cujo pool de Registrador principal não está mais disponível serão direcionados automaticamente para o pool de registradores de backup.

As etapas a seguir descrevem o processo de descoberta e registro do cliente:

1. Um cliente descobre o Skype for Business Server por meio de registros SRV DNS. No Skype for Business Server, os registros SRV DNS podem ser configurados para retornar mais de um FQDN para a consulta SRV dns. Por exemplo, se a empresa Contoso tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de Diretores em cada site central, os registros SRV DNS poderão apontar para os FQDNs do pool de Diretores em cada um dos três locais. Enquanto o pool de Diretores em um dos locais está disponível, o cliente pode se conectar ao Skype for Business Server de primeiro salto.

    > [!NOTE]
    > Usar um pool de Diretores é opcional. Um pool de Front-End pode ser usado em vez disso.

2. O pool de Diretores informa ao cliente Skype for Business sobre o pool de Registradores Registradores primário do usuário e o pool de Registradores De backup.

3. O cliente Skype for Business tenta se conectar ao pool de Registradores Registradores primário do usuário primeiro. Se o pool de Registradores Primários estiver disponível, o Registrador aceitará o registro. Se o pool de Registradores Primários estiver indisponível, o cliente skype for Business tentará se conectar ao pool de registradores de backup. Se o pool de Registradores De backup estiver disponível e tiver determinado que o pool de Registradores Registradores primário do usuário não está disponível (detectando uma falta de pulsação para um intervalo de failover especificado), o pool de registradores de backup aceitará o registro do usuário. Depois que o Registrador de backup detectar que o Registrador primário está novamente disponível, o pool de registradores de backup redireciona os clientes de failover para seu pool primário.

### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Os seguintes requisitos e recomendações para implementar a resiliência de voz do site central são apropriados para a maioria das organizações:

- Os sites nos quais residem os pools de Registradores Registradores primários e de backup devem ser conectados por um link WAN resiliente.

- Cada site central deve conter um pool de Registrador consistindo em um ou mais Registradores.

- Cada pool do Registrador deve ter balanceamento de carga usando balanceamento de carga DNS, balanceamento de carga de hardware ou ambos. Para obter informações detalhadas sobre como planejar sua configuração de balanceamento de carga, consulte Requisitos de balanceamento de [carga do Skype for Business.](../../plan-your-deployment/network-requirements/load-balancing.md)

- Cada usuário deve ser atribuído a um pool de Registradores Primário usando o cmdlet **set-CsUser** do Shell de Gerenciamento do Skype for Business Server ou o Painel de Controle do Skype for Business Server.

- O pool de Registradores Registradores primário deve ter um único pool de registradores de backup localizado em um site central diferente.

- O pool de Registradores Registradores primário deve ser configurado para fazer fail over para o pool de registradores de backup. Por padrão, o Registrador primário é definido para fazer fail over para o pool de registradores de backup após um intervalo de 300 segundos. Você pode alterar esse intervalo usando o Construtor de Topologias do Skype for Business Server.

- Configurar uma rota de failover. Ao configurar a rota, especifique um gateway que está localizado em um site diferente do gateway especificado na rota primária.

- Se o site central contiver seu servidor de gerenciamento principal e o site provavelmente ficar ino mesmo por um longo período, você precisará reinstalar suas ferramentas de gerenciamento no site de backup; caso contrário, você não poderá alterar as configurações de gerenciamento.

### <a name="dependencies"></a>Dependências

O Skype for Business Server depende dos seguintes componentes de software e infraestrutura para garantir a resiliência de voz:

|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolvendo registros SRV e registros A para conectividade servidor-servidor e servidor-cliente  <br/> |
|Exchange e Serviços Web do Exchange (EWS)  <br/> |Armazenamento de contatos; dados de calendário  <br/> |
|Unificação de Mensagens do Exchange e Serviços Web do Exchange  <br/> |Logs de chamadas, lista de caixa postal, caixa postal  <br/> |
|Opções 120 do DHCP  <br/> |Se o DNS SRV não estiver disponível, o cliente tentará usar a Opção 120 do DHCP para descobrir o Registrador. Para que isso funcione, um servidor DHCP deve ser configurado ou o DHCP do Skype for Business Server deve estar habilitado.  <br/> |

### <a name="survivable-voice-features"></a>Recursos de voz que sãovivíveis

Se os requisitos e recomendações anteriores foram implementados, os seguintes recursos de voz serão fornecidos pelo pool de registradores de backup:

- Chamadas PSTN de saída

- Chamadas PSTN de entrada, se o provedor de serviços de telefonia suportar a capacidade de fazer fail over para um site de backup

- Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes

- Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

- Mensagens instantâneas de duas partes e compartilhamento de áudio e vídeo entre usuários no mesmo site

- Encaminhamento de chamada, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se ambas as partes da delegação de chamada, ou todos os membros da equipe, estão configuradas no mesmo site.

- Os telefones e clientes existentes continuam a funcionar.

- CDR (registro de detalhes das chamadas)

- Autenticação e autorização

Dependendo de como eles estão configurados, os seguintes recursos de voz podem ou não funcionar quando um site central primário está fora de serviço:

- Depósito e recuperação de caixa postal

    Se você quiser disponibilizar a UM do Exchange quando o site central principal estiver fora de serviço, faça o seguinte:

  - Altere os registros DNS SRV para que os servidores um do Exchange no site central apontem para os servidores de UM do Exchange em outro local.

  - Configure o plano de discagem de UM do Exchange de cada usuário para incluir servidores um do Exchange no site central e no site de backup, mas designe os servidores um do Exchange de backup como desabilitados. Se o site primário ficar indisponível, o administrador do Exchange terá que marcar os servidores UM do Exchange no site de backup como habilitados.

    Se nenhuma das soluções anteriores for possível, a UM do Exchange não estará disponível caso o site central fique indisponível.

- Conferência de todos os tipos

    Um usuário que fez o failed over para um site de backup pode ingressar em uma conferência criada ou hospedada por um organizador cujo pool está disponível, mas não pode criar ou hospedar uma conferência em seu próprio pool principal, que não está mais disponível. Da mesma forma, outros usuários não podem ingressar em conferências hospedadas no pool primário do usuário afetado.

Os seguintes recursos de voz não funcionam quando um site central primário está fora de serviço:

- Atendente Automático de Conferência

- Roteamento baseado em DND e presença

- Atualizando as configurações de encaminhamento de chamada

- Serviço de Grupo de Resposta e Estacionamento de Chamada

- Provisionando novos telefones e clientes

- Pesquisa da Web do Address Book

## <a name="branch-site-resiliency"></a>Resiliência de site de filial

Se você quiser fornecer resiliência de site de filial, ou seja, o serviço enterprise Voice de alta disponibilidade, você tem três opções para fazer isso:

- Aplicativo de Filial Persistente

- Survivable Branch Server

- Uma implantação completa do Skype for Business Server no site de filial

Este guia ajudará você a avaliar qual solução de resiliência é melhor para a organização e, com base em sua solução de resiliência, a solução de conectividade PSTN a ser usada. Ele também o ajuda a se preparar para implantar a solução escolhida, descrevendo os pré-requisitos e outras considerações de planejamento.

### <a name="branch-site-resiliency-features"></a>Recursos de resiliência do site de filial

Se você fornecer resiliência de site de filial, se a conexão WAN de um site de filial a um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz deverão continuar disponíveis:

- Chamadas PSTN (rede telefônica pública comutado) de entrada e saída

- Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes

- Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

- Mensagens instantâneas de duas partes

- Encaminhamento de chamada, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se o delegante e o representante (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe estão configurados no mesmo site

- Registros de detalhes das chamada (CDRs)

- Conferência de discagem PSTN com Atendedor Automático de Conferência

- Recursos de caixa postal, se você definir as configurações de rerotinação de caixa postal.

- Autenticação e autorização de usuário

Os seguintes recursos estarão disponíveis somente se sua solução de resiliência for uma implantação completa do Skype for Business Server no site de filial:

- Conferência de IM, Web e A/V

- Roteamento baseado em Presença e Não Incomodar (DND) (onde as chamadas são impedidas de tocar em ramais que têm o DND ativado)

- Atualizando as configurações de encaminhamento de chamada

- Aplicativo Grupo de Resposta e aplicativo Estacionamento de Chamada

- Provisionamento de novos telefones e clientes, mas somente se o Active Directory Domain Services estiver presente no site de filial.

- Enhanced 9-1-1 (E9-1-1)

    Se o E9-1-1 estiver implantado e o tronco SIP no local central não estiver disponível porque o link WAN está inocável, o Aparelho de FilialVivível encaminhará as chamadas E9-1-1 para o gateway de filial local. Para habilitar esse recurso, as políticas de voz dos usuários do site de filial devem rotear chamadas para o gateway local em caso de falha da WAN.

> [!NOTE]
> O SBA (escritório de filial sobrevivência) não é suportado para XMPP. Os usuários que estão em uma configuração do SBA não poderão enviar mensagens IMs ou ver a Presença com contatos XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluções de resiliência de site de filial

Há vantagens óbvias em fornecer resiliência de site de filial à sua organização. Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão a ter o serviço do Enterprise Voice e a caixa postal (se você definir as configurações de redirecionamento de caixa postal). No entanto, para sites com menos de 25 usuários, uma solução de resiliência pode não fornecer um retorno suficiente sobre o investimento.

Se decidir fornecer a resiliência do site de filial, você tem três opções. Use a tabela a seguir para ajudá-lo a determinar qual opção é a melhor para sua organização.

|**Se você…**|**Recomendamos que você use um(a)…**|
|:-----|:-----|
|Hospede entre 25 e 1.000 usuários no seu site de filial se o retorno sobre o investimento não suportar uma implantação completa ou em um local em que o suporte administrativo não estiver disponível  <br/> |Aplicativo de Filial Persistente  <br/> O Aparelho de Filial Resistente é um servidor blade padrão do setor com um Registrador e Servidor de Mediação do Skype for Business Server em execução no Windows Server 2008 R2. O Aparelho de Filial Survivível também contém um gateway PSTN (rede telefônica pública comutado). Dispositivos qualificados de terceiros (desenvolvidos pelos parceiros da Microsoft no programa de qualificação/certificação SBA [aparelho de filial persistente]) fornece uma conexão PSTN contínua caso uma WAN falhe, mas essa abordagem não fornece a presença e a conferência resilientes porque esses recursos dependem do servidores Front-End no site central.  <br/> Para obter detalhes sobre Aparelhos de FilialVivíveis, consulte "Detalhes do Aparelho de FilialVivível", posteriormente neste tópico.  <br/> **Observação:** Se você também decidir usar um tronco SIP com seu Aparelho de Filial Confiável, entre em contato com seu fornecedor de Aparelho de Filial Confiável para saber qual é o melhor provedor de serviços para sua organização. <br/> |
|Hospedar entre 1.000 e 2.000 usuários em seu site de filial, não ter uma conexão WAN resiliente e ter administradores treinados do Skype for Business Server disponíveis  <br/> |Servidor de FilialVivível ou dois Aparelhos de FilialVivível.  <br/> O Servidor de Filial Survivable é um Windows Server que está a fim de atender aos requisitos de hardware especificados que têm o Registrador do Skype for Business Server e o software do Servidor de Mediação instalados nele. Ele deve ser conectado a um gateway PSTN ou a um tronco SIP a um provedor de serviço telefônico.  <br/> Para obter detalhes sobre Os Servidores de FilialVivíveis, consulte "Detalhes do Servidor de FilialVivível", posteriormente neste tópico.  <br/> |
|Se você precisar de recursos de presença e conferência além de recursos de voz para até 5.000 usuários e tiver treinado administradores do Skype for Business Server disponíveis  <br/> |Implante como um site central com um servidor Standard Edition e não como um site de filial.  <br/> Uma implantação completa do Skype for Business Server oferece uma conexão PSTN contínua e presença e conferência resilientes em caso de falha de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologia de resiliência

A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.

**Opções de resiliência do site de filial**

![Opções de Resiliência de Filial de Voz](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalhes do aparelho de filial persistente

O Aparelho de FilialVivível do Skype for Business Server inclui os seguintes componentes:

- Um Registrador para a autenticação do usuário, registro e roteamento de chamada

- Um Servidor de Mediação para a manipulação de sinalização entre o Registrador e o gateway PSTN

- Um gateway PSTN para o roteamento de chamadas ao PSTN como um transporte fallback no caso de uma interrupção da WAN

- SQL Server Express para armazenamento de dados do usuário local

O Aparelho de Filial Survivable também inclui troncos PSTN, portas analógicas e um adaptador Ethernet.

Se a conexão WAN do site de filial a um site central ficar indisponível, os usuários internos de filial continuarão a ser registrados com o Registrador de Aparelho de Filial Contínua e obterão o serviço de voz ininterrupto usando a conexão do Aparelho de Filial Survivível com a PSTN. Os usuários do site de filial que se conectam de casa ou de outro locais remotos serão capazes de se registrar com um servidor Registrador em um site central quando um link de WAN ao site de filial estiver indisponível. Esses usuários terão a funcionalidade de comunicações completamente unificadas com única exceção de que as chamadas de entrada ao site de filial irão para a caixa postal. Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deve ser restabelecida aos usuários do site de filial. Nem o failover para o Aparelho de FilialVivível nem a restauração do serviço exigem a presença de um administrador de IT.

O Skype for Business Server dá suporte a até dois Aparelho de FilialVivível em um site de filial.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Visão geral de implantação de aparelho de filial persistente

O Aparelho de Filial Survivable é fabricado por fabricantes de equipamento original em parceria com a Microsoft e implantado em nome deles por varejistas de valor agregado. Essa implantação deve ocorrer somente depois que o Skype for Business Server tiver sido implantado no site central, uma conexão WAN com o site de filial está no local e os usuários do site de filial estão habilitados para o Enterprise Voice.

Para obter detalhes sobre essas fases, consulte [Deploying a Survivable Branch Appliance or Server](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) na documentação de Implantação.

|**Fase**|**Etapas**|**Direitos do usuário**|
|:-----|:-----|:-----|
|Configurar os Serviços de Domínio do Active Directory para o Aparelho de FilialVivível  <br/> |**No site central:** <br/>  Crie uma conta de usuário de domínio (ou identidade corporativa) para o técnico que instalará e ativará o Aparelho de Filial Sobrevivência no site de filial. <br/>  Crie uma conta de computador (com o FQDN (nome de domínio totalmente qualificado) aplicável) para o Aparelho de Filial Survivable nos Serviços de Domínio do Active Directory. <br/>  No Construtor de Topologias, crie e publique o Aparelho de FilialVivível. <br/> |O usuário técnico deve ser um membro do RTCUniversalSBATechnicians. O Aparelho de Filial Remanescente deve pertencer ao grupo RTCSBAUniversalServices, que acontece automaticamente quando você usa o Construtor de Topologias.  <br/> |
|Instale e ative o Aparelho de Filial Sobrevivência.  <br/> |**No site de filial:** <br/>  Conecte o Aparelho de Filial Survivível a uma porta Ethernet e porta PSTN. <br/>  Inicie o Aparelho de FilialVivível. <br/>  In join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site. Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador. <br/>  Configure o Aparelho de Filial Survivível usando a interface do usuário OEM. <br/>  Teste a conectividade do PSTN. <br/> |O usuário técnico deve ser um membro do RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalhes do servidor de filial persistente

No Construtor de Topologias, crie o site de filial, adicione o Servidor de Filial Survivable a esse site e execute o Assistente de Implantação do Skype for Business Server no computador em que você deseja instalar a função.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resiliência do site de filial

Este tópico ajudará a você preparar usuários para resiliência de site de filial e persistência da caixa postal, e também especifica os requisitos de hardware e software importantes.


#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparação de usuários da filial para resiliência de site de filial

Prepare os usuários para resiliência do site de filial definindo seu pool de Registrador como o Aparelho de Filial Survivável (SBA) ou Servidor de Filial Survivable.

#### <a name="registrar-assignments-for-branch-users"></a>Atribuições do registrador avançado para usuários da filial

Independentemente da solução de resiliência do site de filial escolhida, você precisará atribuir um Registrador primário a cada usuário. Os usuários do site de filial devem sempre se registrar com o Registrador no site de filial, independentemente de o Registrador residir no Aparelho de Filial Survivível, no Servidor de Filial Autônomo ou no Skype for Business Server Standard ou no servidor Enterprise Edition. Um registro de recurso de serviço (SRV) de sistema de nome de domínio (DNS) é necessário para que o cliente possa descobrir seu pool de Registrador. Se o Aparelho de Filial Survivível ficar indisponível, é assim que os clientes do site de filial descobrirão automaticamente o Registrador de backup.

Se um site de filial não tiver um servidor DNS, há duas maneiras alternativas de configurar a descoberta do Aparelho de FilialVivível ou do Servidor de Filial Survivável:

- Configure a opção 120 do DHCP no servidor DHCP (Dynamic Host Configuration Protocol) do site de filial para apontar para o FQDN (nome de domínio totalmente qualificado) do Aparelho de FilialVivível ou Servidor de FilialVivível.

- Configure o Aparelho de Filial Survivável ou Servidor de Filial Survivável para responder a consultas DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Roteamento de voz para usuários de filial

É recomendável criar uma política separada de VoIP (Voice over Internet Protocol ) no nível do usuário para usuários em um site de filial. Essa política deve incluir uma rota principal que usa o Aparelho de Filial Existente ou gateway de servidor de filial e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comutado) no local central. Se a rota principal estiver indisponível, a rota de backup que usa um ou mais gateways do site central será utilizada. Dessa forma, independentemente de onde um usuário está registrado — no Registrador de site de filial ou no pool de registradores de backup no site central — a política voIP do usuário está sempre em vigor. Esta é uma consideração importante para cenários de failover. Por exemplo, se você precisar renomear o Aparelho de Filial Sustentável ou reconfigurar o Aparelho de Filial Sustentável para se conectar a um pool de Registradores De backup no site central, deverá mover os usuários do site de filial para o site central durante esse período. (Para obter detalhes sobre como renomear ou reconfigurar um Aparelho de FilialVivível, consulte o Apêndice [B: Gerenciando](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) um Aparelho de FilialVivível na documentação de Implantação.) Se esses usuários não possuem políticas VoIP no nível do usuário ou planos de discagem no nível do usuário, quando os usuários são movidos para outro site, as políticas VoIP em nível de site e os planos de discagem de nível de site do site central se aplicam aos usuários por padrão, em vez das políticas VoIP e planos de discagem no nível do site de filial. Neste cenário, a menos que as políticas de VoIP e planos de discagem de nível de site usados pelo pool de registradores de backup também possam ser aplicadas aos usuários do site de filial, suas chamadas falharão. Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmund, um plano de discagem com regras de normalização que precedam +1425 a todas as chamadas de 7 dígitos provavelmente não traduzirá chamadas de forma apropriada para estes usuários.

> [!IMPORTANT]
> Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de utilização de telefone do PSTN à política do usuário do escritório da filial e atribuir rotas separadas para cada uma. A primeira rota, ou principal, direcionaria chamadas para o gateway associado ao Aparelho de Filial Survivável (SBA) ou servidor de filial; a segunda rota, ou backup, direcionaria chamadas para o gateway no site central. Ao direcionar chamadas, o SBA ou servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso do PSTN antes de tentar o segundo registro de uso.

Para ajudar a garantir que as chamadas de entrada para usuários do site de filial cheguem a esses usuários quando o gateway de filial ou o componente do Windows do site de Aparelho de FilialVivível não estiver disponível (o que ocorreria, por exemplo, se o Aparelho de Filial ESuperativa ou o gateway de filial não estivesse disponível para manutenção), crie uma rota de failover no gateway (ou trabalhe com seu provedor DID (Discagem Direta interna) para redirecionar chamadas de entrada para o pool do Registrador de backup no site central. Daí, as chamadas serão roteadas sobre o link WAN para os usuários da filial. Certifique-se de que a rota traduz números para estar em conformidade com o gateway PSTN ou outros formatos de número de telefone aceitos pelo par de tronco. Para detalhes sobre a criação de uma rota de failover, consulte [Configuring a Failover Route](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Crie também planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial para normalizar chamadas de entrada. Se você tiver dois Aparelhos de Filial Sobrevivência em um site de filial, poderá criar um plano de discagem de nível de site para ambos, a menos que seja necessário um plano de nível de serviço separado para cada um.

> [!NOTE]
> Para suportar o consumo dos recursos do site central pelos usuários de qualquer site de filial que se apoiem no site central para presença, conferência ou failover, é recomendável considerar cada usuário de site de filial como se estivesse registrado no site central. Atualmente, não há limites para o número de usuários do site de filial, incluindo usuários registrados em um Aparelho de FilialVivível.

Também é recomendável criar um plano de discagem de nível de usuário e uma política de voz e atribuí-los a usuários do site de filial. Para obter detalhes, [consulte Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and Create the [VoIP Routing Policy for Branch Users](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) in the Deployment documentation.

#### <a name="routing-extension-numbers"></a>Números de extensão de roteamento

Ao preparar planos de discagem e políticas de voz para usuários do site de filial, certifique-se de incluir regras de normalização e regras de conversão que corresponderem às cadeias de caracteres e ao formato de número usados no atributo de linha msRTCSIP (ou URI de Linha), para que as chamadas do Skype for Business habilitadas entre usuários do site de filial e usuários do site central sejam roteados corretamente, especialmente quando as chamadas devem ser redirecionadas pela PSTN porque o link WAN não está disponível. Existem considerações especiais adicionais para números discados que contêm números de extensão, em vez de apenas números de telefone.

Regras de normalização e de tradução que correspondam a URIs de Linha que contêm um número de extensão, seja de forma exclusiva ou além de um número de telefone totalmente E.164, possuem requisitos adicionais. Esta seção descreve vários cenários de exemplo para rotear chamadas para URIs de Linha com um número de extensão.

Se sua organização não possui Números Fixos Virtuais (DID) configurados para usuários individuais e a URI de Linha de cada usuário está configurada apenas com um número de extensão, usuários internos podem ligar uns para os outros discando apenas um número de extensão. No entanto, é necessário configurar regras de normalização que possam se aplicar a chamadas a partir de um site de filial para um usuário do site central que correspondam a números de extensão.

Em um cenário onde o link WAN entre um site de filial e um site central esteja disponível, chamadas de usuários do site de filial para usuários do site central não exigem que a regra de normalização correspondente traduza o número porque a chamada não é roteada sobre o PSTN. Por exemplo:

|**Nome da regra**|**Descrição**|**Padrão de número**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Não traduz números de 5 dígitos  <br/> |^(\d {5} )$  <br/> |$1  <br/> |10001 não é traduzido  <br/> |

Você também deve acomodar números de extensão para cenários específicos, como quando o link WAN entre um site de filial e o site central está indisponível e um chamada de um site de filial deve ser roteada através do PSTN. Durante uma paralisação WAN, se um usuário do site de filial ligar para um usuário do site central apenas discando o ramal do usuário do site central, você deverá ter uma regra de conversão de saída que adiciona o número de telefone completo do usuário do site central. Se o URI de Linha de um usuário contiver o número de telefone completo da sua organização e o número de ramal exclusivo do usuário em vez de um número de telefone completo exclusivo para o usuário, você deverá ter uma regra de conversão de saída que, em vez disso, você deverá ter uma regra de conversão de saída que adiciona o número de telefone completo da sua organização. Por exemplo:

|**Descrição**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Converte números de 5 dígitos para o número de telefone e ramal de um usuário  <br/> |^(\d {5} )$  <br/> |+14255550123;ext=$1  <br/> |10001 é traduzido como +14255550123;ext=10001  <br/> |
|Converte números de 5 dígitos no número de telefone da sua organização e no ramal de um usuário  <br/> |^(\d {5} )$  <br/> |+14255550100;ext=$1  <br/> |10001 é traduzido como +14255550100;ext=10001  <br/> |

Neste cenário, se o ponto do tronco que trata o re-roteamento para o PSTN não suportar os números de extensão, a regra de tradução de saída também deve remover o número de extensão. Por exemplo:

|**Descrição**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Remove a extensão dos números de telefone com extensões  <br/> |^\+(\d \* ); ext=(\d \* )$  <br/> |+$1  <br/> |+14255550123;ext=10001 é traduzido como +14255550123  <br/> |

Se um link WAN estiver disponível ou não, se sua organização não tiver números DID configurados para usuários individuais e o URI de Linha de um usuário contiver o número de telefone da sua organização e o número de ramal exclusivo do usuário, você deverá configurar o URI da Linha do número de telefone da sua organização com um número que seja acessível pelo par de tronco ou gateway PSTN no site de filial. Você também deve configurar o URI de Linha do número de telefone da sua organização para incluir seu próprio ramal exclusivo para que as chamadas sejam roteados para esse número.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparação para persistência de caixa postal

A Unificação de Mensagens (UM) do Exchange normalmente é instalada apenas em um site central e não em sites de filiais. Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo se o link WAN entre o site da filial e o site central estiver indisponível. Como resultado, a configuração do URI de Linha para o número de telefone do Atendente Automático da UM do Exchange que fornece caixa postal para usuários do site de filial exige considerações especiais, além da política de voz, do plano de discagem e das regras de normalização aplicáveis a esse número de caixa postal.

Os SBAs (Aparelhos de Filial Sustentáveis) e os Servidores de Filial Sustentáveis fornecem a sobrevivência da caixa postal para usuários de filiais durante uma paralisação wan. Especificamente, se você estiver usando um Aparelho de Filial Survivable ou Servidor de Filial Survivable e a WAN ficar indisponível, o SBA ou o Servidor de Filial Survivable redireciona chamadas não respondidas sobre o PSTN para a UM do Exchange no site central. Com um SBA ou Servidor de FilialVivível, os usuários também podem recuperar mensagens de caixa postal por meio da PSTN durante uma paralisação wan. Por fim, durante uma inativação da WAN, o Aparelho de Filial Survivable ou Servidor de Filial Survivível enfileia notificações de chamada perdida e as carrega no servidor um do Exchange quando a WAN é restaurada. Para ajudar a garantir que o reroque da caixa postal seja resiliente, certifique-se de adicionar uma entrada para o FQDN do pool de site central e uma entrada para o FQDN do Servidor de Borda para o arquivo de hosts no Servidor de Filial Persistente. Do contrário, a resolução do DNS pode ultrapassar o tempo se não houver um servidor DNS no site da filial.

Recomendamos seguir as configurações a seguir para a persistência de caixa postal para usuários de filiais:

- Um administrador do Microsoft Exchange deve configurar o AA (Exchange UM Auto Attendant) para aceitar apenas mensagens. Esta configuração desabilita todas as outras funcionalidades genéricas, como transferência para um usuário ou transferência para um operador e limita o AA a aceitar apenas mensagens. Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado para rotear a chamada para um operador.

- O administrador do Skype for Business Server deve usar o número de telefone do AA e usá-lo como o número de atendimento automático do UM do **Exchange** nas configurações de rerotinação de caixa postal para o Aparelho de Filial Survivável ou servidor de filial.

- O administrador do Skype for Business Server deve obter o número  de telefone de acesso do assinante da UM do Exchange e usar esse número como o número de acesso do assinante nas configurações de rerotação de caixa postal para o Aparelho de Filial Survivável ou Servidor de FilialVivível.

- O administrador do Skype for Business Server deve configurar a UM do Exchange para que apenas um plano de discagem seja associado a todos os usuários de filial que precisam acessar a caixa postal durante uma paralisação wan.

- Quando o link WAN não estiver disponível, as chamadas para usuários do site de filial poderão ser roteadas para a caixa de correio de voz da UM (Unificação de Mensagens) do Exchange do usuário, mas somente se a política de voz aplicada à chamada especificar um número de telefone de caixa postal exclusivo e que não inclua um número de ramal.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware e software para resiliência de site de filial

Os requisitos de hardware e software variam, dependendo da sua solução de resiliência.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para Aparelhos de Filial Persistente

O hardware e o software necessários são integrados ao Aparelho de Filial Survivável. No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter endereços IP clientes; do contrário, quando a concessão do DHCP expirar, os clientes não terão conectividade IP.

Se os servidores DNS corporativos estão localizados apenas em sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma paralisação wan e, portanto, a descoberta do Skype for Business Server que usa o registro de recurso DNS SRV (serviço )) falhará. Para garantir o re-roteamento imediato durante uma interrupção da WAN, registros DNS devem ser armazenados em cache no site da filial. Se o roteador da filial for compatível, ative o cache do DNS. Ou você pode implantar um servidor DNS na filial. Pode ser um servidor autônomo ou uma versão do Aparelho de FilialVivível que oferece suporte a recursos dns. Para obter detalhes, entre em contato com seu provedor de Aparelho de FilialVivível.

> [!NOTE]
> Não é necessário ter um controlador de domínio no site da filial. O Aparelho de Filial Survivível autentica clientes usando um certificado especial que envia ao cliente em resposta à solicitação de certificado do cliente ao entrar.

Os clientes do Skype for Business podem descobrir o Skype for Business Server usando a Opção 120 do DHCP (Opção registrador SIP). Ela pode ser configurada em uma de duas formas:

- Configure o servidor DHCP no site de filial para responder a consultas do DHCP 120, que retornam o FQDN do Registrador no Aparelho de Filial Survivável ou Servidor de FilialVivível.

- Ativar o DHCP do Skype for Business Server. Quando isso está ligado, o Registrador do Skype for Business Server responde às consultas da Opção 120 do DHCP. Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente da Opção 120 do DHCP.

Além disso, para sites de filial maiores, que possuem várias sub-redes, agentes de retransmissão DHCP devem estar habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).

Por fim, os usuários do site de filial devem ser configurados para o Enterprise Voice e provisionados com um ponto de extremidade de comunicações unificadas apropriado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para Servidores de Filial Persistente

Os requisitos para Servidores de FilialVivíveis são os mesmos dos requisitos para um Servidor Front-End. Para obter detalhes, [consulte Requisitos de servidor para o Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos para Full-Scale implantações de Branch-Site Skype for Business Server

Para obter detalhes, [consulte Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) in the Planning documentation.

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
| Rota Local de Redmond  <br/> | ^\+1(425           | 206                     | 253)(\d {7} )$  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Rota Local de Dallas  <br/>  | ^\+1(972           | 214                     | 469)(\d {7} )$  <br/>                       | Local  <br/>                                    |
| Rota Universal  <br/>     | ^\+? \*(\d) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Rota de Usuários de Dallas  <br/>  | ^\+? \*(\d) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.


