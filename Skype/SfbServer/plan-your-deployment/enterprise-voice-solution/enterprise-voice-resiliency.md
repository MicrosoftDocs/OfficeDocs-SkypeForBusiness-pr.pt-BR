---
title: Planejar Enterprise Voice resiliência no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: Saiba como dar suporte à resiliência de voz Skype for Business Server Enterprise Voice, em sites centrais e sites de filial. As opções de site de filial incluem a implantação de Aparelhos de Filial Desaviváveis ou Servidores de Filial Desaviváveis.
ms.openlocfilehash: a2dc18817f28595cdfdf65be35df85d0ad93239b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851875"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planejar Enterprise Voice resiliência no Skype for Business Server

Saiba como dar suporte à resiliência de voz Skype for Business Server Enterprise Voice, em sites centrais e sites de filial. As opções de site de filial incluem a implantação de Aparelhos de Filial Desaviváveis ou Servidores de Filial Desaviváveis.

A resiliência de voz refere-se à capacidade dos usuários de continuar fazendo e recebendo chamadas se um site central que hospeda Skype for Business Server ficar indisponível, seja por meio de uma falha de rede de ampla área (WAN) ou outra causa. Se um site central falhar, Enterprise Voice serviço deve continuar ininterrupto por meio do failover contínuo para um site de backup. Em caso de falha na WAN, as chamadas de site de filial devem ser redirecionadas para um gateway PSTN local. Esta seção discute o planejamento da resiliência de voz em caso de falha de WAN ou de site central.

## <a name="central-site-resiliency"></a>Resiliência de site central

Cada vez mais, as empresas têm vários sites espalhados pelo mundo. A manutenção de serviços de emergência, o acesso ao help desk e a capacidade de conduzir tarefas comerciais críticas quando um site central está fora de serviço é essencial para qualquer solução de Enterprise Voice de resiliência. Quando um site central fica indisponível, as seguintes condições devem ser atendidas:

- O failover de voz deve ser fornecido.

- Os usuários que normalmente se registram com o pool de Front-End no site central devem ser capazes de se registrar com um pool de Front-End alternativo. Isso pode ser feito criando vários registros SRV DNS, cada um deles resolvido para um pool de Diretores ou um pool de Front-End em cada um dos seus sites centrais. Você pode ajustar a prioridade e os pesos dos registros SRV para que os usuários atendidos por esse site central recebam o Diretor e o pool de Front-End correspondentes à frente daqueles em outros registros SRV.

- As chamadas de usuários localizados em outros sites devem ser redirecionadas para a PSTN.

Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.

### <a name="architecture-and-topology"></a>Arquitetura e Topologia

O planejamento da resiliência de voz em um site central requer uma compreensão básica da função central desempenhada pelo Registrador Skype for Business Server na habilitação do failover de voz. O Skype for Business Server é um serviço que permite o registro e autenticação do cliente e fornece serviços de roteamento. Ele é executado em todos os servidores Edição Standard, Servidor Front-End, Diretor ou Aparelho de Filial Desavivável. Um pool de Registradores consiste em Serviços do Registrador em execução no pool de Front-End e residindo no mesmo site. Um Skype for Business cliente descobre o pool de Front-End por meio do seguinte mecanismo de descoberta:

1. Registro SRV de DNS

2. Serviço Web de Descoberta Automática

3. Opção DHCP 120

Depois que Skype for Business cliente se conecta ao pool de Front-End, ele é direcionado pelo balanceador de carga a um dos Servidores Front-End no pool. Esse Servidor Front-End, por sua vez, redireciona o cliente para um Registrador preferencial no pool.

Cada usuário habilitado para Enterprise Voice é atribuído a um pool de Registrador específico, que se torna o pool de Registradores principal do usuário. Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de Registradores primário. Para levar em conta o consumo de recursos de site central por qualquer usuário de site de filial que dependa do site central para presença, conferência ou failover, recomendamos que você considere cada usuário de site de filial como se o usuário fosse um usuário registrado no site central. No momento, não há limites no número de usuários de site de filial, incluindo usuários registrados com um Aparelho de Filial Desavivável.

Para garantir a resiliência de voz em caso de falha de site central, o pool de Registradores principal deve ter um único pool de Registrador de backup designado localizado em outro site. O backup pode ser configurado usando configurações de resiliência do Construtor de Topologias. Supondo que um link wan resiliente entre os dois sites, os usuários cujo pool principal de Registradores não está mais disponível são direcionados automaticamente para o pool de Registradores de backup.

As etapas a seguir descrevem o processo de descoberta e registro do cliente:

1. Um cliente descobre Skype for Business Server por meio de registros SRV DNS. No Skype for Business Server, os registros SRV DNS podem ser configurados para retornar mais de um FQDN à consulta DNS SRV. Por exemplo, se a contoso empresarial tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de Diretores em cada site central, os registros SRV DNS poderão apontar para os FQDNs do pool de diretores em cada um dos três locais. Enquanto o pool de Diretores em um dos locais está disponível, o cliente pode se conectar ao primeiro salto Skype for Business Server.

    > [!NOTE]
    > Usar um pool de Diretores é opcional. Em vez disso, um pool de Front-End pode ser usado.

2. O pool de diretores informa o Skype for Business cliente sobre o pool de Registradores principal do usuário e o pool de Registradores de backup.

3. O Skype for Business cliente tenta se conectar primeiro ao pool de Registradores principal do usuário. Se o pool de Registradores primário estiver disponível, o Registrador aceitará o registro. Se o pool de Registradores primário estiver indisponível, o cliente Skype for Business tentar se conectar ao pool de Registradores de backup. Se o pool de Registradores de backup estiver disponível e tiver determinado que o pool de Registradores principal do usuário está indisponível (detectando uma falta de pulsação para um intervalo de failover especificado), o pool de registradores de backup aceitará o registro do usuário. Depois que o Registrador de backup detectar que o Registrador principal está novamente disponível, o pool de registradores de backup redireciona os clientes de failover para o pool principal.

### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Os seguintes requisitos e recomendações para implementar a resiliência de voz do site central são apropriados para a maioria das organizações:

- Os sites nos quais residem os pools de Registradores primários e de backup devem ser conectados por um link WAN resiliente.

- Cada site central deve conter um pool de Registradores que consiste em um ou mais Registradores.

- Cada pool de Registradores deve ter balanceamento de carga usando balanceamento de carga DNS, balanceamento de carga de hardware ou ambos. Para obter informações detalhadas sobre como planejar sua configuração de balanceamento de carga, consulte [Requisitos](../../plan-your-deployment/network-requirements/load-balancing.md)de balanceamento de carga para Skype for Business .

- Cada usuário deve ser atribuído a um pool de Registradores primário usando o cmdlet Skype for Business Server Shell de Gerenciamento **set-CsUser** ou o painel de controle Skype for Business Server de gerenciamento.

- O pool principal do Registrador deve ter um único pool de Registrador de backup localizado em um site central diferente.

- O pool de Registradores primário deve ser configurado para fail over para o pool de registradores de backup. Por padrão, o Registrador principal é definido como fail over para o pool de Registradores de backup após um intervalo de 300 segundos. Você pode alterar esse intervalo usando o Construtor Skype for Business Server Topologia.

- Configurar uma rota de failover. Ao configurar a rota, especifique um gateway localizado em um site diferente do gateway especificado na rota primária.

- Se o site central contiver seu servidor de gerenciamento principal e o site provavelmente ficar para baixo por um longo período, você precisará reinstalar suas ferramentas de gerenciamento no site de backup; caso contrário, você não poderá alterar as configurações de gerenciamento.

### <a name="dependencies"></a>Dependências

Skype for Business Server depende dos seguintes componentes de infraestrutura e software para garantir a resiliência de voz:

|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolução de registros SRV e registros A para conectividade servidor-servidor e servidor-cliente  <br/> |
|Exchange e Exchange Web Services (EWS)  <br/> |Armazenamento de contatos; dados de calendário  <br/> |
|Exchange Unificação de Mensagens e serviços Web Exchange Web  <br/> |Logs de chamada, lista de caixa postal, caixa postal  <br/> |
|Opções DHCP 120  <br/> |Se o DNS SRV não estiver disponível, o cliente tentará usar a Opção DHCP 120 para descobrir o Registrador. Para que isso funcione, um servidor DHCP deve ser configurado ou Skype for Business Server DHCP deve ser habilitado.  <br/> |

### <a name="survivable-voice-features"></a>Recursos de Voz Suportáveis

Se os requisitos e recomendações anteriores foram implementados, os seguintes recursos de voz serão fornecidos pelo pool de Registradores de backup:

- Chamadas PSTN de saída

- Chamadas PSTN de entrada, se o provedor de serviços de telefonia suportar a capacidade de fazer fail over para um site de backup

- Enterprise chamadas entre usuários no mesmo site e entre dois sites diferentes

- Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

- Mensagens instantâneas de duas partes e compartilhamento de áudio e vídeo entre usuários no mesmo site

- Encaminhamento de chamada, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se ambas as partes para chamar a delegação ou todos os membros da equipe estão configuradas no mesmo site.

- Telefones e clientes existentes continuam a funcionar.

- CDR (registro de detalhes das chamadas)

- Autenticação e autorização

Dependendo de como eles são configurados, os seguintes recursos de voz podem ou não funcionar quando um site central principal está fora de serviço:

- Depósito e recuperação de caixa postal

    Se você quiser disponibilizar Exchange UM quando o site central principal estiver fora de serviço, faça um dos seguintes:

  - Altere registros SRV DNS para que os Exchange de UM no site central apontem para fazer backup Exchange servidores de UM em outro site.

  - Configure o Exchange plano de discagem de UM de cada usuário para incluir Exchange de UM no site central e no site de backup, mas designe os servidores de UM de backup Exchange como desabilitados. Se o site principal ficar indisponível, o administrador Exchange deve marcar os Exchange de UM no site de backup conforme habilitado.

    Se nenhuma das soluções anteriores for possível, Exchange UM não estará disponível no caso de o site central ficar indisponível.

- Conferência de todos os tipos

    Um usuário que falhou em um site de backup pode ingressar em uma conferência criada ou hospedada por um organizador cujo pool está disponível, mas não pode criar ou hospedar uma conferência em seu próprio pool principal, que não está mais disponível. Da mesma forma, outros usuários não podem ingressar em conferências hospedadas no pool principal do usuário afetado.

Os seguintes recursos de voz não funcionam quando um site central principal está fora de serviço:

- Atendimento Automático de Conferência

- Roteamento baseado em presença e DND

- Atualizando configurações de encaminhamento de chamada

- Serviço do Grupo de Resposta e Estacionamento de Chamada

- Provisionamento de novos telefones e clientes

- Pesquisa da Web do Livro de Endereços

## <a name="branch-site-resiliency"></a>Resiliência de site de filial

Se você deseja fornecer resiliência de branch-site, ou seja, serviço de alta disponibilidade Enterprise Voice, você tem três opções para fazer isso:

- Aplicativo de Filial Persistente

- Survivable Branch Server

- Uma implantação Skype for Business Server no site de filial

Este guia ajudará você a avaliar qual solução de resiliência é melhor para a organização e, com base em sua solução de resiliência, a solução de conectividade PSTN a ser usada. Ele também o ajuda a se preparar para implantar a solução escolhida, descrevendo os pré-requisitos e outras considerações de planejamento.

### <a name="branch-site-resiliency-features"></a>Recursos de resiliência de site de filial

Se você fornecer resiliência de site de filial, se a conexão WAN de um site de filial a um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz devem continuar disponíveis:

- Chamadas de rede telefônica pública comutado de entrada e saída (PSTN)

- Enterprise chamadas entre usuários no mesmo site e entre dois sites diferentes

- Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

- Mensagens instantâneas de duas partes

- Encaminhamento de chamada, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se o delegador e representante (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe estão configurados no mesmo site

- Registros de detalhes de chamada (CDRs)

- Conferência de discagem PSTN com Atendedor Automático de Conferência

- Recursos de caixa postal, se você definir configurações de redirecionar a caixa postal.

- Autenticação e autorização de usuário

Os seguintes recursos estarão disponíveis somente se sua solução de resiliência for uma implantação de Skype for Business Server em escala completa no site de filial:

- Conferência de IM, Web e A/V

- Roteamento baseado em Presença e Não Incomodar (DND) (onde as chamadas são impedidas de tocar em extensões que tenham o DND ativado)

- Atualizando configurações de encaminhamento de chamada

- Aplicativo do Grupo de Resposta e aplicativo estacionamento de chamada

- Provisionando novos telefones e clientes, mas somente se o Active Directory Domain Services estiver presente no site da filial.

- 9-1-1 aprimorado (E9-1-1)

    Se o E9-1-1 for implantado e o tronco SIP no site central não estiver disponível porque o link WAN está inostado, o Aparelho de Filial Desavivável encaminhará as chamadas E9-1-1 para o gateway de filial local. Para habilitar esse recurso, as políticas de voz dos usuários de filial devem encaminhar chamadas para o gateway local em caso de falha na WAN.

> [!NOTE]
> O SBA (filial que pode sobreviver) não é suportado para XMPP. Os usuários que estão em uma configuração do SBA não poderão enviar mensagens IMs ou ver Presença com contatos XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluções de resiliência de site de filial

Há vantagens óbvias em fornecer resiliência de filial para sua organização. Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão Enterprise Voice serviço e caixa postal (se você configurar configurações de redirecionamento de caixa postal). No entanto, para sites com menos de 25 usuários, uma solução de resiliência pode não fornecer um retorno suficiente sobre o investimento.

Se decidir fornecer a resiliência do site de filial, você tem três opções. Use a tabela a seguir para ajudá-lo a determinar qual opção é a melhor para sua organização.

|**Se você…**|**Recomendamos que você use um(a)…**|
|:-----|:-----|
|Hospede entre 25 e 1.000 usuários no seu site de filial se o retorno sobre o investimento não suportar uma implantação completa ou em um local em que o suporte administrativo não estiver disponível  <br/> |Aplicativo de Filial Persistente  <br/> O Aparelho de Filial Resistente é um servidor de folha padrão do setor com um registrador Skype for Business Server e Servidor de Mediação em execução no Windows Server 2008 R2. O Aparelho de FilialVivível também contém um gateway PSTN (rede telefônica pública comutado). Dispositivos qualificados de terceiros (desenvolvidos pelos parceiros da Microsoft no programa de qualificação/certificação SBA [aparelho de filial persistente]) fornece uma conexão PSTN contínua caso uma WAN falhe, mas essa abordagem não fornece a presença e a conferência resilientes porque esses recursos dependem do servidores Front-End no site central.  <br/> Para obter detalhes sobre Aparelhos de Filial Suportáveis, consulte "Detalhes do Aparelho de Filial Suportável", mais adiante neste tópico.  <br/> **Observação:** Se você decidir também usar um tronco SIP com seu Aparelho de Filial Desavivável, entre em contato com o fornecedor do Aparelho de Filial Para saber mais sobre qual provedor de serviços é o melhor para sua organização. <br/> |
|Hospedar entre 1000 e 2000 usuários em seu site de filial, não possui uma conexão WAN resiliente e ter Skype for Business Server administradores disponíveis  <br/> |Servidor de Filial Desavivável ou dois Aparelhos de Filial Suportáveis.  <br/> O Servidor de Filial Desavivável é uma reunião de Windows server requisitos de hardware especificados que Skype for Business Server software do Registrador e do Servidor de Mediação instalados nele. Ele deve ser conectado a um gateway PSTN ou a um tronco SIP a um provedor de serviço telefônico.  <br/> Para obter detalhes sobre Servidores de Filial Desaviváveis, consulte "Detalhes do Servidor de Filial Suportável", mais adiante neste tópico.  <br/> |
|Se você precisar de recursos de presença e conferência, além de recursos de voz para até 5.000 usuários, e tiver treinado Skype for Business Server administradores disponíveis  <br/> |Implante como um site central com um servidor Standard Edition e não como um site de filial.  <br/> Uma implantação de Skype for Business Server de escala completa fornece uma conexão PSTN contínua e presença resiliente e conferência em caso de falha de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologia de resiliência

A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.

**Opções de resiliência do site de filial**

![Opções de Resiliência de Filial de Voz.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalhes do aparelho de filial persistente

O Skype for Business Server Aparelho de Filial Desavivável inclui os seguintes componentes:

- Um Registrador para a autenticação do usuário, registro e roteamento de chamada

- Um Servidor de Mediação para a manipulação de sinalização entre o Registrador e o gateway PSTN

- Um gateway PSTN para o roteamento de chamadas ao PSTN como um transporte fallback no caso de uma interrupção da WAN

- SQL Server Express para armazenamento de dados do usuário local

O Aparelho de Filial Suportável também inclui troncos PSTN, portas analógicas e um adaptador Ethernet.

Se a conexão WAN do site de filial a um site central ficar indisponível, os usuários de filial interna continuarão a ser registrados com o Registrador de Aparelhos de Filial E obterão o serviço de voz ininterrupto usando a conexão aparelho de filial de manutenção com a PSTN. Os usuários do site de filial que se conectam de casa ou de outro locais remotos serão capazes de se registrar com um servidor Registrador em um site central quando um link de WAN ao site de filial estiver indisponível. Esses usuários terão a funcionalidade de comunicações completamente unificadas com única exceção de que as chamadas de entrada ao site de filial irão para a caixa postal. Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deve ser restabelecida aos usuários do site de filial. Nem o failover para o Aparelho de Filial Desavivável nem a restauração do serviço exige a presença de um administrador de IT.

Skype for Business Server suporta até dois Aparelhos de Filial Desaviváveis em um site de filial.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Visão geral de implantação de aparelho de filial persistente

O Aparelho de Filial Desavivável é fabricado por fabricantes de equipamentos originais em parceria com a Microsoft e implantado em seu nome por varejistas com valor agregado. Essa implantação deve ocorrer somente depois que Skype for Business Server tiver sido implantada no site central, uma conexão WAN com o site de filial está no local e os usuários do site de filial estão habilitados para Enterprise Voice.

Para obter detalhes sobre essas fases, consulte [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) na documentação de Implantação.

|**Fase**|**Etapas**|**Direitos do usuário**|
|:-----|:-----|:-----|
|Configurar os Serviços de Domínio do Active Directory para o Aparelho de Filial Suportável  <br/> |**No site central:** <br/>  Crie uma conta de usuário de domínio (ou identidade corporativa) para o técnico que instalará e ativará o Aparelho de Filial Suportável no site da filial. <br/>  Crie uma conta de computador (com o FQDN (nome de domínio totalmente qualificado) aplicável para Aparelho de Filial Desavivável nos Serviços de Domínio do Active Directory. <br/>  No Construtor de Topologias, crie e publique o Aparelho de Filial Suportável. <br/> |O usuário técnico deve ser um membro do RTCUniversalSBATechnicians. O Aparelho de Filial Remanescente deve pertencer ao grupo RTCSBAUniversalServices, que acontece automaticamente quando você usa o Construtor de Topologias.  <br/> |
|Instale e ative o Aparelho de Filial Suportável.  <br/> |**No site de filial:** <br/>  Conexão o Aparelho de Filial Suportável para uma porta Ethernet e porta PSTN. <br/>  Inicie o Aparelho de Filial Desavivável. <br/>  Ins join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site. Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador. <br/>  Configure o Aparelho de Filial Suportável usando a interface do usuário OEM. <br/>  Teste a conectividade do PSTN. <br/> |O usuário técnico deve ser um membro do RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalhes do servidor de filial persistente

No Construtor de Topologias, crie o site de filial, adicione o Servidor de FilialVivível a esse site e execute o Assistente de Implantação Skype for Business Server no computador onde você deseja instalar a função.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resiliência de site de filial

Este tópico ajudará a você preparar usuários para resiliência de site de filial e persistência da caixa postal, e também especifica os requisitos de hardware e software importantes.


#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparação de usuários da filial para resiliência de site de filial

Prepare os usuários para resiliência do site de filial definindo seu pool de Registradores como o Dispositivo de Filial Desavivável (SBA) ou Servidor de Filial Desavivável.

#### <a name="registrar-assignments-for-branch-users"></a>Atribuições do registrador avançado para usuários da filial

Independentemente de qual solução de resiliência de site de filial você escolher, você precisará atribuir um Registrador primário a cada usuário. Os usuários do site de filial sempre devem se registrar com o Registrador no site de filial, independentemente de o Registrador residir no Aparelho de Filial Suportável, Servidor de Filial Desavivável ou servidor autônomo Skype for Business Server Standard ou Edição Enterprise. Um registro de recurso de serviço (SRV) de sistema de nome de domínio (DNS) é necessário para que o cliente possa descobrir seu pool de Registrador. Se o Aparelho de Filial Suportável ficar indisponível, é assim que os clientes de site de filial descobrirão automaticamente o Registrador de backup.

Se um site de filial não tiver um servidor DNS, há duas maneiras alternativas de configurar a descoberta do Aparelho de Filial Suportável ou do Servidor de Filial Desavivável:

- Configure a opção DHCP 120 no servidor DHCP (Dynamic Host Configuration Protocol) do site de filial para apontar para o FQDN (nome de domínio totalmente qualificado) do Aparelho de Filial Desavivável ou Servidor de Filial Desavivável.

- Configure o Aparelho de Filial Suportável ou o Servidor de FilialVivível para responder às consultas DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Roteamento de voz para usuários de filial

É recomendável criar uma política separada de VoIP (Voice over Internet Protocol ) no nível do usuário para usuários em um site de filial. Essa política deve incluir uma rota primária que usa o Aparelho de Filial Existente ou gateway de servidor de filial e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comutado) no site central. Se a rota principal estiver indisponível, a rota de backup que usa um ou mais gateways do site central será utilizada. Dessa forma, independentemente de onde um usuário está registrado no Registrador do site de filial ou no pool de Registradores de backup no site central, a política VoIP do usuário está sempre em vigor. Esta é uma consideração importante para cenários de failover. Por exemplo, se você precisar renomear o Aparelho de Filial Desavivável ou reconfigurar o Aparelho de Filial Desavivável para se conectar a um pool de Registradores de backup no site central, você deverá mover os usuários do site de filial para o site central durante a duração. (Para obter detalhes sobre como renomear ou reconfigurar um Aparelho de Filial Desavivável, consulte Apêndice B: Managing [a Survivable Branch Appliance](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) na documentação de implantação.) Se esses usuários não têm políticas VoIP no nível do usuário ou planos de discagem no nível do usuário, quando os usuários são movidos para outro site, as políticas VoIP no nível do site e os planos de discagem no nível do site central se aplicam aos usuários por padrão, em vez das políticas voIP no nível do site de filial e planos de discagem,. Neste cenário, a menos que as políticas de VoIP e planos de discagem de nível de site usados pelo pool de registradores de backup também possam ser aplicadas aos usuários do site de filial, suas chamadas falharão. Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmund, um plano de discagem com regras de normalização que precedam +1425 a todas as chamadas de 7 dígitos provavelmente não traduzirá chamadas de forma apropriada para estes usuários.

> [!IMPORTANT]
> Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de utilização de telefone do PSTN à política do usuário do escritório da filial e atribuir rotas separadas para cada uma. A primeira rota, ou primária, direcionaria chamadas para o gateway associado ao SBA (Aparelho de Filial Suportável) ou servidor de filial; a segunda rota, ou backup, direcionaria chamadas para o gateway no site central. Ao direcionar chamadas, o SBA ou servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso do PSTN antes de tentar o segundo registro de uso.

Para ajudar a garantir que as chamadas de entrada para usuários de site de filial cheguem a esses usuários quando o gateway de filial ou o componente Windows do site aparelho de filial não estiver disponível (o que ocorreria, por exemplo, se o Aparelho de Filial Ou gateway de filial que estava para manutenção), crie uma rota de failover no gateway (ou trabalhe com seu provedor de Discagem Direta Interna (DID) para redirecionar chamadas de entrada para o pool do Registrador de backup no pool central site. Daí, as chamadas serão roteadas sobre o link WAN para os usuários da filial. Certifique-se de que a rota traduz números para estar em conformidade com o gateway PSTN ou outros formatos de número de telefone aceitos do par de tronco. Para detalhes sobre a criação de uma rota de failover, consulte [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). Crie também planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial para normalizar chamadas de entrada. Se você tiver dois Aparelhos de FilialVivíveis em um site de filial, poderá criar um plano de discagem no nível do site para ambos, a menos que seja necessário um plano de nível de serviço separado para cada um.

> [!NOTE]
> Para suportar o consumo dos recursos do site central pelos usuários de qualquer site de filial que se apoiem no site central para presença, conferência ou failover, é recomendável considerar cada usuário de site de filial como se estivesse registrado no site central. No momento, não há limites no número de usuários de site de filial, incluindo usuários registrados com um Aparelho de Filial Desavivável.

Também é recomendável criar um plano de discagem de nível de usuário e uma política de voz e atribuí-los a usuários do site de filial. Para obter detalhes, [consulte Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and Create the [VoIP Routing Policy for Branch Users](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) na documentação implantação.

#### <a name="routing-extension-numbers"></a>Números de extensão de roteamento

Ao preparar planos de discagem e políticas de voz para usuários de site de filial, certifique-se de incluir regras de normalização e regras de conversão que corresponderem às cadeias de caracteres e formato de número usados no atributo msRTCSIP-line (ou URI de linha), para que as chamadas Skype for Business habilitadas entre usuários de site de filial e usuários de site central sejam roteados corretamente— especialmente quando as chamadas devem ser redirecionadas pelo PSTN porque o link wan está indisponível. Existem considerações especiais adicionais para números discados que contêm números de extensão, em vez de apenas números de telefone.

Regras de normalização e de tradução que correspondam a URIs de Linha que contêm um número de extensão, seja de forma exclusiva ou além de um número de telefone totalmente E.164, possuem requisitos adicionais. Esta seção descreve vários cenários de exemplo para rotear chamadas para URIs de Linha com um número de extensão.

Se sua organização não possui Números Fixos Virtuais (DID) configurados para usuários individuais e a URI de Linha de cada usuário está configurada apenas com um número de extensão, usuários internos podem ligar uns para os outros discando apenas um número de extensão. No entanto, é necessário configurar regras de normalização que possam se aplicar a chamadas a partir de um site de filial para um usuário do site central que correspondam a números de extensão.

Em um cenário onde o link WAN entre um site de filial e um site central esteja disponível, chamadas de usuários do site de filial para usuários do site central não exigem que a regra de normalização correspondente traduza o número porque a chamada não é roteada sobre o PSTN. Por exemplo:

|**Nome da regra**|**Descrição**|**Padrão de número**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Não traduz números de 5 dígitos  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 não é traduzido  <br/> |

Você também deve acomodar números de extensão para cenários específicos, como quando o link WAN entre um site de filial e o site central está indisponível e um chamada de um site de filial deve ser roteada através do PSTN. Durante uma paralisação wan, se um usuário de site de filial chamar um usuário de site central apenas discando a extensão do usuário do site central, você deve ter uma regra de conversão de saída que adiciona o número de telefone completo do usuário do site central. Se o URI de linha de um usuário contiver o número de telefone completo da sua organização e o número de ramal exclusivo do usuário, em vez de um número de telefone completo exclusivo para o usuário, você deve ter uma regra de conversão de saída que adiciona o número de telefone completo da sua organização. Por exemplo:

|**Descrição**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Converte números de 5 dígitos para o número de telefone e extensão de um usuário  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 é traduzido como +14255550123;ext=10001  <br/> |
|Converte números de 5 dígitos para o número de telefone da sua organização e a extensão de um usuário  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 é traduzido como +14255550100;ext=10001  <br/> |

Neste cenário, se o ponto do tronco que trata o re-roteamento para o PSTN não suportar os números de extensão, a regra de tradução de saída também deve remover o número de extensão. Por exemplo:

|**Descrição**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Remove a extensão dos números de telefone com extensões  <br/> |^\+(\d \* ); ext=(\d \* )$  <br/> |+$1  <br/> |+14255550123;ext=10001 é traduzido como +14255550123  <br/> |

Se um link WAN estiver ou não disponível, se sua organização não tiver números DID configurados para usuários individuais e o URI de linha para um usuário contiver o número de telefone da sua organização e o número de ramal exclusivo do usuário, você deverá configurar o URI de Linha de Linha do número de telefone da sua organização com um número que seja acessível pelo par de tronco ou gateway PSTN no site de filial. Você também deve configurar o URI de linha de número de telefone da sua organização para incluir sua própria extensão exclusiva para que as chamadas sejam roteados para esse número.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparação para persistência de caixa postal

Exchange A Unificação de Mensagens (UM) geralmente é instalada apenas em um site central e não em sites de filial. Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo se o link WAN entre o site da filial e o site central estiver indisponível. Como resultado, a configuração do URI de linha para o número de telefone Atendedor Automático da UM Exchange que fornece caixa postal para usuários de site de filial requer considerações especiais, além da política de voz, plano de discagem e regras de normalização aplicáveis a esse número de caixa postal.

Os Dispositivos de Filial (SBAs) e Os Servidores de Filial Suportáveis fornecem capacidade de sobrevivência de caixa postal para usuários de filial durante uma paralisação de WAN. Especificamente, se você estiver usando um Aparelho de Filial Desavivável ou Servidor de Filial Desavivável e a WAN ficar indisponível, o SBA ou Servidor de Filial Desavivável redireciona chamadas não respondidas pelo PSTN para Exchange UM no site central. Com um SBA ou Servidor de Filial Desavivável, os usuários também podem recuperar mensagens de caixa postal por meio do PSTN durante uma paralisação de WAN. Por fim, durante uma inativa WAN, o Aparelho de Filial Desavivável ou Servidor de Filial Desavivável faz filas de notificações de chamada perdida e, em seguida, carrega-as no servidor de UM Exchange quando a WAN é restaurada. Para ajudar a garantir que a redirecionação de caixa postal seja resiliente, certifique-se de adicionar uma entrada para o FQDN do pool de sites central e uma entrada para o FQDN do Servidor de Borda ao arquivo hosts no Servidor de Filial Persistente. Do contrário, a resolução do DNS pode ultrapassar o tempo se não houver um servidor DNS no site da filial.

Recomendamos seguir as configurações a seguir para a persistência de caixa postal para usuários de filiais:

- Um administrador Exchange microsoft deve configurar Exchange um Atendedor Automático (AA) para aceitar apenas mensagens. Esta configuração desabilita todas as outras funcionalidades genéricas, como transferência para um usuário ou transferência para um operador e limita o AA a aceitar apenas mensagens. Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado para rotear a chamada para um operador.

- O Skype for Business Server administrador deve usar o número de telefone AA e usar esse número de telefone como o número de atendimento automático de um do **exchange** nas configurações de redirecionação de caixa postal para o Aparelho de Filial Ou servidor de filial do Exchange.

- O Skype for Business Server administrador deve obter o número de telefone de acesso do  assinante de UM Exchange e usar esse número como o número de acesso do assinante nas configurações de redirecionação de caixa postal para o Aparelho de Filial ESuperável ou o Servidor de Filial Desavivável.

- O Skype for Business Server administrador deve configurar Exchange UM para que apenas um plano de discagem seja associado a todos os usuários de filial que precisam de acesso à caixa postal durante uma paralisação de WAN.

- Quando o link WAN estiver indisponível, as chamadas aos usuários do Exchange site de filial podem ser roteadas para a caixa de correio de voz da UM (Unificação de Mensagens) do usuário, mas somente se a política de voz aplicada à chamada especificar um número de telefone de caixa postal exclusivo e não incluir um número de ramal.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware e software para resiliência de site de filial

Os requisitos de hardware e software variam, dependendo da sua solução de resiliência.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para Aparelhos de Filial Persistente

O hardware e o software necessários são integrados ao Aparelho de Filial Desavivável. No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter endereços IP clientes; do contrário, quando a concessão do DHCP expirar, os clientes não terão conectividade IP.

Se os servidores DNS corporativos estão localizados apenas em sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma falha de WAN e, portanto, uma descoberta Skype for Business Server que usa o registro de recurso dns SRV (serviço (SRV) falhará. Para garantir o re-roteamento imediato durante uma interrupção da WAN, registros DNS devem ser armazenados em cache no site da filial. Se o roteador da filial for compatível, ative o cache do DNS. Ou você pode implantar um servidor DNS na filial. Pode ser um servidor autônomo ou uma versão do Aparelho de Filial Que dá suporte a recursos DNS. Para obter detalhes, entre em contato com seu provedor de Aparelho de Filial Desavivável.

> [!NOTE]
> Não é necessário ter um controlador de domínio no site da filial. O Aparelho de Filial Suportável autentica clientes usando um certificado especial que envia o cliente em resposta à solicitação de certificado do cliente ao entrar.

Skype for Business os clientes podem descobrir o Skype for Business Server usando a opção DHCP 120 (Opção de Registrador SIP). Ela pode ser configurada em uma de duas formas:

- Configure o servidor DHCP no site da filial para responder às consultas DHCP 120, que retornam o FQDN do Registrador no Aparelho de Filial Desavivável ou Servidor de Filial Desavivável.

- A Skype for Business Server DHCP. Quando isso é ligado, o registrador Skype for Business Server responde às consultas da Opção DHCP 120. Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente da Opção 120 do DHCP.

Além disso, para sites de filial maiores, que possuem várias sub-redes, agentes de retransmissão DHCP devem estar habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).

Por fim, os usuários do site de filial devem ser configurados para Enterprise Voice e provisionados com um ponto de extremidade de comunicação unificada apropriado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para Servidores de Filial Persistente

Os requisitos para Servidores de Filial Suportáveis são os mesmos dos requisitos para um Servidor Front-End. Para obter detalhes, consulte [Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos para Full-Scale Skype for Business Server Branch-Site implantações

Para obter detalhes, consulte [Requisitos do servidor Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) na documentação planejamento.

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
| Rota Universal  <br/>     | ^\+? (\d \* ) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Rota de Usuários de Dallas  <br/>  | ^\+? (\d \* ) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.