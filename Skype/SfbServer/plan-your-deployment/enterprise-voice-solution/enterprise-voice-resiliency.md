---
title: Plan for Enterprise Voice resiliency in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Saiba como dar suporte à resiliência de voz no Skype for Business Server Enterprise Voice, em sites centrais e em sites de filiais. As opções de site de filiais incluem a implantação de aparelhos de ramificação sobreviventes ou servidores de ramificação sobreviventes.
ms.openlocfilehash: e64ac79ef49339401c5b2d0bbb7d27140eca4296
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802941"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Plan for Enterprise Voice resiliency in Skype for Business Server

Saiba como dar suporte à resiliência de voz no Skype for Business Server Enterprise Voice, em sites centrais e em sites de filiais. As opções de site de filiais incluem a implantação de aparelhos de ramificação sobreviventes ou servidores de ramificação sobreviventes.

A resiliência de voz refere-se à capacidade de os usuários continuarem a fazer e receber chamadas se um site central que hospeda o Skype for Business Server ficar indisponível, seja por meio de uma falha de rede de longa distância (WAN) ou outra causa. Se um local central falhar, o serviço do Enterprise Voice deverá continuar sem interrupções por meio de failover direto para um local de backup. No caso de uma falha de WAN, as chamadas do local de filial deverão ser redirecionadas para um gateway PSTN local. Esta seção discute o planejamento de resiliência de voz no caso de uma falha do local central ou de WAN.

## <a name="central-site-resiliency"></a>Resiliência do local central

Cada vez mais, as empresas possuem vários sites espalhados por todo o mundo. A manutenção de serviços de emergência, o acesso ao suporte técnico e a capacidade de conduzir tarefas essenciais para empresas quando um site central está fora do serviço é essencial para qualquer solução de resiliência de voz corporativa. Quando um site central torna-se indisponível, as seguintes condições devem ser atendidas:

- O failover de voz deve ser fornecido.

- Os usuários que normalmente se registram com o pool de front-end no site central devem ser capazes de se registrar com um pool de front-end alternativo. Isso pode ser feito criando vários registros SRV DNS, cada um deles resolve para um pool de directors ou um pool de front-end em cada um dos seus sites centrais. Você pode ajustar a prioridade e os pesos dos registros SRV para que os usuários que são servidos por esse site central obtenham o diretor e o pool de front-end correspondentes à frente daqueles em outros Registros SRV.

- As chamadas para/de usuários localizados em outros sites devem ser reencaminhadas para a PSTN.

Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.

### <a name="architecture-and-topology"></a>Arquitetura e topologia

Planejar a resiliência de voz em um site central requer uma compreensão básica da função central executada pelo registrador do Skype for Business Server para habilitar o failover de voz. O registrador do Skype for Business Server é um serviço que permite registro e autenticação do cliente e fornece serviços de roteamento. Ele é executado em todos os aplicativos Standard Edition, servidor front-end, diretor ou em filiais sobreviventes. Um pool de registrador consiste em serviços de registrador em execução no pool de front-ends e no mesmo site. Um cliente Skype for Business descobre o pool de front-end por meio do seguinte mecanismo de descoberta:

1. Registro SRV de DNS

2. Serviço Web de Descoberta Automática

3. Opção 120 do DHCP

Depois que o cliente Skype for Business se conecta ao pool de front-end, ele é direcionado pelo balanceador de carga para um dos servidores de front-end do pool. Esse servidor front-end, por sua vez, redireciona o cliente para um registrador preferencial no pool.

Cada usuário habilitado para o Enterprise Voice é atribuído a um pool de registrador específico, que se torna o pool de registradores primários do usuário. Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de Registradores Avançados primário. Para calcular o consumo de recursos do site central pelos usuários do site de filial que dependem do site central para presença, conferência ou failover, recomendamos considerar cada usuário do site de filial como se fosse um usuário registrado no site central. No momento, não há limites quanto ao número de usuários de sites de filiais, incluindo usuários registrados em um aparelho de ramificação sobreviventes.

Para garantir a resiliência de voz em caso de uma falha do site central, o pool de Registradores Avançados primário deve ter um único pool de Registradores Avançados de backup designado localizado em outro site. O backup pode ser configurado usando as configurações de resiliência do construtor de topologia. Supondo que haja um link WAN resiliente entre os dois sites, os usuários cujo pool de Registradores Avançados primário não está mais disponível serão direcionados automaticamente para pool de backup.

As etapas a seguir descrevem o processo de descoberta e registro de clientes:

1. Um cliente descobre o Skype for Business Server por meio de registros SRV DNS. No Skype for Business Server, os registros SRV DNS podem ser configurados para retornar mais de um FQDN para a consulta SRV DNS. Por exemplo, se a empresa Contoso tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de Diretores em cada um desses sites, os registros DNS SRV poderão apontar para os FQDNs do pool de Diretores em cada um dos três locais. Desde que o pool do diretor de um dos locais esteja disponível, o cliente pode se conectar ao primeiro nó do Skype for Business Server.

    > [!NOTE]
    > Usar um pool de diretor é opcional. Um pool de front-ends pode ser usado em vez disso.

2. O pool de directors informa ao cliente do Skype for Business sobre o pool de registradores primários do usuário e o pool de registrador de backup.

3. O cliente Skype for Business tenta se conectar ao pool de registradores primários do usuário primeiro. Se esse pool estiver disponível, o Registrador Avançado aceitará o registro. Se o pool de registrador primário estiver indisponível, o cliente Skype for Business tentará se conectar ao pool de registradores de backup. Se o pool de registrador de backup estiver disponível e tiver determinado que o pool de registradores primários do usuário não está disponível (detectando a falta de pulsação para um intervalo de failover especificado), o pool de registrador de backup aceita o registro do usuário. Depois que o Registrador Avançado de backup detectar que o Registrador Avançado primário está novamente disponível, o pool de backup redirecionará os clientes de failover para seu pool primário.

### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Os seguintes requisitos e recomendações para a implementação da resiliência de voz do site central são apropriados para a maioria das organizações:

- Os sites nos quais residem os pools de Registradores Avançados primário e de backup devem estar conectados por um link WAN resiliente.

- Cada site central deve conter um pool de Registradores Avançados que consiste em um ou mais Registradores Avançados.

- Cada pool de Registradores Avançados deve ter sua carga balanceada por meio do balanceamento de carga DNS, do balanceamento de carga de hardware ou de ambos. Para obter informações detalhadas sobre como planejar a configuração de balanceamento de carga, consulte [requisitos de balanceamento de carga para o Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).

- Cada usuário deve ser atribuído a um pool principal de registradores usando o cmdlet **set-CsUser** do Shell de gerenciamento do Skype for Business Server ou o painel de controle do Skype for Business Server.

- O pool primário deve ter um único pool de backup localizado em um site central diferente.

- O pool de Registradores Avançados primário deve ser configurado de modo que seja feito o seu failover para o pool de Registradores Avançados de backup. Por padrão, o Registrador primário é definido para que esse failover ocorra após um intervalo de 300 segundos. Você pode alterar esse intervalo usando o construtor de topologias do Skype for Business Server.

- Configure uma rota de failover. Ao configurar a rota, especifique um gateway que está localizado em um site diferente do gateway especificado na rota primária.

- Se o site central continha seu servidor de gerenciamento principal e se o site estiver inoperante por um período prolongado, será necessário reinstalar as ferramentas de gerenciamento no local de backup; caso contrário, você não poderá alterar nenhuma configuração de gerenciamento.

### <a name="dependencies"></a>Dependências

O Skype for Business Server depende dos seguintes componentes de infraestrutura e software para garantir a resiliência de voz:

|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolver registros SRV e registros A para conectividade de servidor-servidor e servidor-cliente  <br/> |
|Exchange e Serviços Web do Exchange (EWS)  <br/> |Armazenamento de contatos; dados do calendário  <br/> |
|Unificação de Mensagens do Exchange e Serviços Web do Exchange  <br/> |Logs de chamada, lista de caixas postais, caixa postal  <br/> |
|Opções 120 do DHCP  <br/> |Se o DNS SRV não estiver disponível, o cliente tentará usar a Opção 120 do DHCP para descobrir o Registrador Avançado. Para que isso funcione, um servidor DHCP deve ser configurado ou o DHCP do Skype for Business Server deve estar habilitado.  <br/> |

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

  - Configure o plano de discagem do Exchange UM de cada usuário para incluir servidores do Exchange UM no site central e no site de backup, mas designe os servidores de backup UM do Exchange como desabilitado. Se o site primário ficar indisponível, o administrador do Exchange precisará marcar os servidores do Exchange UM no site de backup como habilitado.

    Se nenhuma das soluções anteriores for possível, o Exchange UM não estará disponível em caso de o site central ficar indisponível.

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

Se você quiser fornecer resiliência de filial do site, ou seja, serviço Enterprise Voice de alta disponibilidade, terá três opções para fazer isso:

- Aparelho de Filial Persistente

- Servidor de Filial Persistente

- Uma implantação completa do Skype for Business Server no site da filial

Este guia ajudará você a avaliar qual solução de resiliência é melhor para a organização e, com base em sua solução de resiliência, a solução de conectividade PSTN a ser usada. Ele também o ajuda a se preparar para implantar a solução escolhida, descrevendo os pré-requisitos e outras considerações de planejamento.

### <a name="branch-site-resiliency-features"></a>Recursos de resiliência do site de filial

Se você fornecer resiliência de filial do site, se a conexão de WAN de um site de filial com um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz devem continuar disponíveis:

- Chamadas de rede de telefonia pública comutada (PSTN) de entrada e saída

- Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes

- Administração básica de chamadas, incluindo espera, recuperação e transferência de chamadas

- Mensagens instantâneas de dois participantes

- Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamadas e serviços de chamada de equipe, mas somente se o delegante e representante (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe, estiverem configurados no mesmo site

- Registros de detalhes de chamadas (CDRs)

- Conferência de discagem PSTN com Atendedor Automático de Conferência

- Recursos de caixa postal, se forem configuradas definições de reroteamento de caixa postal.

- Autenticação e autorização de usuário

Os recursos a seguir estarão disponíveis apenas se a sua solução de resiliência for uma implantação do Skype for Business Server de dimensionamento completo no site da filial:

- Conferências de IM, webconferências e conferências de A/V

- Presença e roteamento baseado em Não Incomodar (DND), onde as chamadas não tocam em extensões com o DND ativado

- Atualização de configurações de encaminhamento de chamadas

- Aplicativo grupo de resposta e aplicativo de estacionamento de chamada

- Provisionar novos telefones e clientes, mas somente se os serviços de domínio Active Directory estiverem presentes no site de filial.

- 9-1-1 Avançado (E9-1-1)

    Se o E9-1-1 estiver implantado e o tronco SIP no site central não estiver disponível porque o link de WAN está indisponível, então o aparelho de ramificação sobreviventes roteará chamadas E9-1-1 para o gateway de filial local. Para habilitar esse recurso, as políticas de voz dos usuários do site de filial devem direcionar chamadas para o gateway local em caso de falha de WAN.

> [!NOTE]
> O SBA (aparelho de filial persistente) não tem suporte no XMPP. Os usuários hospedados em uma configuração do SBA não poderão enviar mensagens de chat nem ver a presença com os contatos do XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluções de resiliência do site de filial

A resiliência de sites de filial proporciona vantagens evidentes à sua organização. Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão a ter serviço Enterprise Voice e correio de voz (se você definir as configurações de redirecionamento de caixa postal). Entretanto, em sites com menos de 25 usuários, a solução de resiliência poderá não gerar um retorno adequado sobre o investimento.

Há três opções para fornecer a resiliência do site de filial. A tabela a seguir o ajudará a determinar qual opção é a melhor para sua organização.

|**Se você…**|**Recomendamos que você use um(a)…**|
|:-----|:-----|
|Hospedar entre 25 e 1.000 usuários no seu site de filial e se o retorno sobre o investimento não permitir uma implantação completa ou quando não houver suporte administrativo local disponível  <br/> |Aparelho de Filial Persistente  <br/> O appliance de ramificação sobreviventes é um servidor blade padrão do setor com um servidor de registrador e mediação do Skype for Business Server executado no Windows Server 2008 R2. O aparelho de ramificação sobreviventes também contém um gateway PSTN (rede telefônica pública comutada). Dispositivos qualificados de terceiros (desenvolvidos por parceiros da Microsoft no programa de qualificação/certificação SBA [Aparelho de Filial Persistente]) fornecem uma conexão PSTN contínua em caso de falha da WAN, mas essa abordagem não oferece presença e conferência resilientes porque esses recursos dependem dos Servidores Front-End do site central.  <br/> Para obter detalhes sobre os aparelhos de ramificação sobreviventes, consulte "detalhes do aplicativo da ramificação sobreviventes", posteriormente neste tópico.  <br/> **Observação:** Se você decidir usar também um tronco SIP com o seu aparelho de ramificação sobreviventes, entre em contato com o fornecedor da sua agência para saber mais sobre qual provedor de serviços é melhor para a sua organização. <br/> |
|Host entre os usuários do 1000 e do 2000 no seu site da sua filial, sem conexão de WAN resistente e com os administradores do Skype for Business Server treinados disponíveis  <br/> |Servidor de ramificação sobreviventes ou dois aparelhos de ramificação sobreviventes.  <br/> O servidor de ramificação sobreviventes é uma reunião do Windows Server que especifica requisitos de hardware que têm o software servidor de mediação e servidor de mediação do Skype for Business Server instalado. Ele deve estar conectado a um provedor de serviços telefônicos por meio de um gateway PSTN ou de um tronco SIP.  <br/> Para obter detalhes sobre os servidores de ramificação sobreviventes, consulte "detalhes do servidor de ramificação sobreviventes", posteriormente neste tópico.  <br/> |
|Se você precisar de recursos de presença e conferência, além de recursos de voz para até 5000 usuários, e tiver treinado os administradores do Skype for Business Server disponíveis  <br/> |Implante como um site central com um servidor Standard Edition e não como um site de filial.  <br/> Uma implantação completa do Skype for Business Server oferece uma conexão PSTN contínua e presença e presença resilientes e conferência em caso de falha de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologias de resiliência

A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.

**Opções de resiliência do site de filial**

![Opções de resiliência de ramificação de voz](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalhes do Aparelho de Filial Persistente

O aplicativo de ramificação do Skype for Business Server para filiais sobreviventes inclui os seguintes componentes:

- Um Registrador Avançado para autenticação do usuário, registro e roteamento de chamadas

- Um Servidor de Mediação para tratar a sinalização entre o Registrador Avançado e o gateway PSTN

- Um gateway PSTN para o roteamento de chamadas para a PSTN como um transporte fallback no caso de uma interrupção da WAN

- O SQL Server Express para armazenamento de dados local do usuário

O aparelho de ramificação sobreviventes também inclui troncos PSTN, portas analógicas e adaptador Ethernet.

Se a conexão de WAN do site de filial com um site central ficar indisponível, os usuários da ramificação interna continuarão a ser registrados com o registrador de appliances da ramificação sobreviventes e obter serviço de voz ininterrupto usando a conexão de aparelho de ramificação sobreviventes para a PSTN. Os usuários do site de filial que se conectarem de casa ou de outros locais remotos serão capazes de se registrar em um servidor do Registrador Avançado em um site central quando um link WAN com o site de filial não estiver disponível. Esses usuários contarão com total funcionalidade de comunicações unificadas, sendo a única exceção as chamadas de entrada para o site de filial, que irão para a caixa postal. Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deverá ser restabelecida para os usuários do site de filial. Nem o failover para o aparelho de ramificação sobreviventes nem a restauração do serviço exige a presença de um administrador de ti.

O Skype for Business Server tem suporte para até dois appliances para filiais sobreviventes em um site de filiais.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Visão geral da implantação do aparelho de filial persistente

O aparelho para filiais sobreviventes é fabricado por fabricantes de equipamento original em parceria com a Microsoft e implantado em nome de revendedores de valor agregado. Essa implantação deve ocorrer somente após a implantação do Skype for Business Server no site central, uma conexão de WAN com o site de filial e os usuários do site da filial serem habilitados para o Enterprise Voice.

Para obter detalhes sobre essas fases, consulte [Deploying a Survivable Branch Appliance or Server](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) na documentação de Implantação.

|**Fase**|**Etapas**|**Direitos do usuário**|
|:-----|:-----|:-----|
|Configurar os serviços de domínio do Active Directory para o aparelho de ramificação sobreviventes  <br/> |**No site central:** <br/>  Crie uma conta de usuário de domínio (ou identidade empresarial) para o técnico que instalará e ativará o aparelho de ramificação sobreviventes no site da filial. <br/>  Crie uma conta de computador (com o nome de domínio totalmente qualificado (FQDN) aplicável) para o aparelho de ramificação sobreviventes nos serviços de domínio Active Directory. <br/>  Em Construtor de topologia, crie e publique o aparelho de ramificação sobreviventes. <br/> |A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians. O aparelho de ramificação sobreviventes deve pertencer ao grupo RTCSBAUniversalServices, que acontece automaticamente quando você usa o construtor de topologias.  <br/> |
|Instale e ative o aparelho de ramificação sobreviventes.  <br/> |**No site de filial:** <br/>  Conecte o aparelho de ramificação sobreviventes a uma porta Ethernet e a uma porta PSTN. <br/>  Inicie o aparelho de ramificação sobreviventes. <br/>  Ingresse na ramificação da ramificação sobreviventes para o domínio usando a conta de usuário do domínio criada para o aparelho de ramificação sobreviventes no site central. Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador. <br/>  Configure o aparelho de ramificação sobreviventes usando a interface de usuário do OEM. <br/>  Teste a conectividade PSTN. <br/> |A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalhes do Servidor de Filial Persistente

Em Construtor de topologias, crie o site de ramificação, adicione o servidor de ramificação sobreviventes a esse site e execute o assistente de implantação do Skype for Business Server no computador onde você deseja instalar a função.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resiliência do site da filial

Este tópico ajudará você a preparar os usuários para resiliência do site de filial e persistência da caixa postal. Ele também especifica os requisitos importantes de hardware e software.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparação de usuários da filial para resiliência do site de filial

Prepare os usuários para a resiliência de site de filial definindo o pool registrador como o aparelho de ramificação sobreviventes (SBA) ou o servidor de ramificação sobreviventes.

#### <a name="registrar-assignments-for-branch-users"></a>Atribuições do Registrador Avançado para usuários da filial

Independentemente da solução de resiliência de site de filial escolhida, será necessário atribuir um Registrador Avançado primário a cada usuário. Os usuários do site de ramificação sempre devem se registrar no registrador de site, independentemente de o registrador residir na ramificação da ramificação sobreviventes, no servidor de ramificação sobreviventes ou no aplicativo autônomo do Skype for Business Server ou Enterprise Edition servidor. Um registro DNS (Sistema de Nomes de Domínio) de recurso de serviços (SRV) é necessário para que o cliente possa descobrir o seu pool de Registradores Avançados. Se o aparelho de ramificação sobreviventes ficar indisponível, é como os clientes do site de filiais detectam automaticamente o registrador de backup.

Se um site de filial não tiver um servidor DNS, existem duas maneiras alternativas para configurar a descoberta do aparelho de ramificação sobreviventes ou do servidor de ramificação sobreviventes:

- Configure a opção de DHCP 120 no servidor DHCP (Dynamic Host Configuration Protocol) para apontar para o nome de domínio totalmente qualificado (FQDN) do aparelho de ramificação sobreviventes ou do servidor de ramificação sobreviventes.

- Configure o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes para responder às consultas de DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Roteamento de voz para usuários de filial

É recomendável criar uma política VoIP separada em nível de usuário para os usuários de um site de filial. Essa política deve incluir uma rota primária que usa o aplicativo de ramificação ou o gateway de servidor de ramificação sobreviventes e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comutada) no site central. Se a rota principal não estiver disponível, a rota de backup que usa um ou mais gateways do site central será utilizada. Dessa forma, independentemente de onde um usuário estiver registrado, no registrador de site de filial ou no pool de registradores de backup no site central, a política de VoIP do usuário estará sempre em vigor. Essa é uma consideração importante para cenários de failover. Por exemplo, se precisar renomear o aparelho de ramificação sobreviventes ou reconfigurar o aparelho de ramificação sobreviventes para se conectar a um pool de registradores de backup no site central, você deverá mover os usuários do site para o site central durante a duração. (Para obter detalhes sobre como renomear ou reconfigurar um aparelho de ramificação sobreviventes, consulte [Apêndice B: gerenciar um aparelho de ramificação sobreviventes](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) na documentação de implantação.) Se esses usuários não tiverem políticas de VoIP em nível de usuário ou planos de discagem em nível de usuário, quando os usuários forem movidos para outro site, as políticas de VoIP no nível do site e os planos de discagem no nível do site central se aplicam aos usuários por padrão, em vez de políticas de VoIP no nível de site e de planos de discagem Nesse cenário, a menos que as políticas VoIP e os planos de discagem em nível de site usados pelo pool de Registradores Avançados de backup também possam ser aplicados aos usuários do site de filial, suas chamadas falharão. Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmond, um plano de discagem com regras de normalização que acrescentem o prefixo +1425 a todas as chamadas de 7 dígitos provavelmente não converterá as chamadas de forma apropriada para esses usuários.

> [!IMPORTANT]
> Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de uso do telefone PSTN à política do usuário do escritório da filial e atribuir rotas separadas a cada um deles. A rota inicial ou primária faria chamadas para o gateway associado à ferramenta de ramificação (SBA) ou ao servidor de ramificação sobreviventes. a rota de segundo, ou backup, direcionaria chamadas para o gateway no site central. Ao direcionar as chamadas, o SBA ou o servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso PSTN, antes de tentar o segundo registro.

Para ajudar a garantir que as chamadas recebidas para os usuários do site de ramificação cheguem a esses usuários quando o gateway da ramificação ou o componente do Windows do site do aparelho de ramificação sobreviventes estiver indisponível (o que aconteceria, por exemplo, se a ramificação ou ramificação sobreviventes pode ser retentada o gateway foi desativado para manutenção), crie uma rota de failover no gateway (ou trabalhe com o seu provedor de discagem direta) para redirecionar as chamadas de entrada para o pool de registradores de backup no site central. A partir desse local, as chamadas serão encaminhadas através do link WAN para os usuários da filial. Certifique-se de que a rota traduz números para obedecer ao gateway PSTN ou a outros formatos de número de telefone aceitos de par de tronco. Para obter detalhes sobre como criar uma rota de failover, consulte [Configuring a Failover Route](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Além disso, crie planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial a fim de normalizar as chamadas de entrada. Se você tiver dois aparelhos de ramificação sobreviventes em um site de filial, poderá criar um plano de discagem em nível de site para ambos, a menos que seja necessário um plano de nível de serviço separado para cada um.

> [!NOTE]
> Para contabilizar o consumo de recursos do site central pelos usuários de um site de filial que dependam do site central para fins de presença, conferência ou failover, é recomendável considerar cada usuário do site de filial como se estivesse registrado no site central. No momento, não há limites quanto ao número de usuários de sites de filiais, incluindo usuários registrados em um aparelho de ramificação sobreviventes.

Também é recomendável criar um plano de discagem e uma política de voz em nível de usuário, e atribuí-los aos usuários do site de filial. Para obter detalhes, consulte [criar ou modificar um plano de discagem no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) e [criar a política de roteamento de VoIP para usuários da ramificação](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) na documentação de implantação.

#### <a name="routing-extension-numbers"></a>Roteamento de números de ramal

Ao preparar planos de discagem e políticas de voz para usuários de site de ramificação, certifique-se de incluir regras de normalização e regras de tradução que correspondam às cadeias de caracteres e o formato de número usados no atributo msRTCSIP-linha (ou URI de linha) para que as chamadas do Skype for Business sejam habilitadas entre os usuários do site da filial e os usuários do site central serão roteados corretamente, principalmente quando as chamadas devem ser redirecionadas pelo PSTN porque o link de rede de longa distância não está disponível. Além disso, há considerações especiais para números discados que contêm números de ramal, e não apenas números de telefone.

As regras de normalização e de conversão que fazem a correspondência das URIs de Linha que contêm um número de ramal, exclusivamente ou além de um número de telefone E.164 completo, têm requisitos adicionais. Esta seção descreve vários cenários de exemplo para encaminhar chamadas para URIs de Linha com um número de ramal.

Se a sua organização não tiver números de telefone de Discagem Direta Interna (DDI) configurados para usuários individuais, e a URI da Linha de cada usuário estiver configurada apenas com um número de ramal, os usuários internos poderão ligar uns para os outros discando apenas um número de ramal. No entanto, é necessário configurar regras de normalização aplicáveis às chamadas de um usuário do site de filial para outro do site central, que façam a correspondência dos números de ramal.

Em um cenário em que o link WAN entre um site de filial e um site central esteja disponível, as chamadas de usuários do site de filial para os do site central não exigirão que a regra de normalização de correspondência converta o número porque a chamada não é encaminhada através da PSTN. Por exemplo:

|**Nome da regra**|**Descrição**|**Padrão de número**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Não converte números de 5 dígitos  <br/> |^ (\d{5}) $  <br/> |$1  <br/> |10001 não é convertido  <br/> |

Você também deve acomodar números de ramal para cenários específicos, como, por exemplo, quando o link WAN entre um site de filial e o site central não está disponível, e uma chamada de um site de filial deve ser encaminhada através da PSTN. Durante uma falha de WAN, se um site de filial chamar um usuário do site central apenas discando a extensão do usuário do site central, você deve ter uma regra de tradução de saída que adiciona o número de telefone completo do usuário do site central. Se o URI de linha de um usuário contiver o número de telefone completo da sua organização e o número de ramal exclusivo do usuário, em vez de um número de telefone completo exclusivo para o usuário, você deve ter uma regra de tradução de saída que adiciona o número de telefone completo da sua organização. em vez disso . Por exemplo:

|**Descrição**|**Padrão correspondente**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Converte números de 5 dígitos no número de telefone e na extensão de um usuário  <br/> |^ (\d{5}) $  <br/> |+14255550123;ext=$1  <br/> |10001 é convertido em +14255550123;ext=10001  <br/> |
|Converte números de 5 dígitos para o número de telefone da sua organização e a extensão de um usuário  <br/> |^ (\d{5}) $  <br/> |+14255550100;ext=$1  <br/> |10001 é convertido em +14255550100;ext=10001  <br/> |

Neste cenário, se o par do tronco que trata do reencaminhamento para a PSTN não aceitar números de ramal, a regra de conversão de saída também deverá remover o número do ramal. Por exemplo:

|**Descrição**|**Padrão correspondente**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Remove o ramal dos números de telefone com ramais  <br/> |^\+(\d\*); ext = (\d\*) $  <br/> |+$1  <br/> |+14255550123;ext=10001 é convertido em +14255550123  <br/> |

Se uma conexão de rede de longa distância estiver disponível, se sua organização não tiver números definidos para usuários individuais e o URI de linha para um usuário contiver o número de telefone da sua organização e o número de ramal exclusivo do usuário, você deverá configurar o URI da linha do número de telefone da organização com um número alcançável pelo par de troncos ou pelo gateway PSTN no site da filial. Você também deve configurar o URI da linha do número de telefone da sua organização para incluir sua própria extensão exclusiva para que as chamadas sejam roteadas para esse número.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparação para persistência da caixa postal

A UM (Unificação de mensagens) do Exchange geralmente é instalada apenas em um site central e não em sites de filiais. Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo que o link WAN entre o site de filial e o central não esteja disponível. Como resultado, a configuração do URI de linha do número de telefone do atendedor automático do Exchange UM que forneça a caixa postal para os usuários do site de ramificação exige considerações especiais, além da política de voz, do plano de discagem e das regras de normalização aplicáveis a essa caixa postal tempo.

Os appliances de ramificação sobreviventes (SBAs) e os servidores de filiais sobreviventes fornecem sustentabilidade da caixa postal para usuários de filiais durante uma falha de WAN. Especificamente, se você estiver usando um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes e a WAN ficar indisponível, o servidor de ramificação SBA ou sobreviver redirecionará chamadas não atendidas pela PSTN para o Exchange UM no site central. Com um servidor de ramificação SBA ou sobreviventes, os usuários também podem recuperar mensagens de caixa postal por meio da PSTN durante uma falha de WAN. Por fim, durante uma falha de WAN, o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes enfileira notificações de chamada perdida e, em seguida, carrega-as para o servidor do Exchange UM quando a WAN é restaurada. Para ajudar a garantir que o redirecionamento de caixa postal seja resistente, certifique-se de adicionar uma entrada para o FQDN do pool de site central e uma entrada para o FQDN do servidor de borda ao arquivo hosts no servidor de ramificação sobreviventes. Caso contrário, o tempo limite da resolução DNS poderá expirar se não houver um servidor DNS no site de filial.

Recomendamos definir as configurações a seguir para a persistência da caixa postal dos usuários do site de filial:

- Um administrador do Microsoft Exchange deve configurar o atendedor automático do Exchange UM para aceitar somente mensagens. Essa configuração desabilita todas as outras funcionalidades genéricas, como a transferência para um usuário ou a transferência para um operador, e limita o AA a aceitar apenas mensagens. Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado a fim de encaminhar a chamada para um operador.

- O administrador do Skype for Business Server deve levar o número de telefone AA e usar esse número de telefone como o número de **atendedor automático de um do Exchange** nas configurações de redirecionamento de caixa postal para o aparelho de ramificação ou servidor de ramificação sobreviventes.

- O administrador do Skype for Business Server deve obter o número de telefone de acesso do assinante do Exchange UM e usar esse número como o número de **acesso do assinante** nas configurações de redirecionamento de caixa postal para o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes.

- O administrador do Skype for Business Server deve configurar o UM do Exchange para que apenas um plano de discagem esteja associado a todos os usuários da ramificação que precisam acessar a caixa postal durante uma falha de WAN.

- Quando o link de rede de longa distância não está disponível, as chamadas para os usuários do site de ramificação podem ser roteadas para a caixa de correio de voz do Exchange Unified Messaging (UM) do Exchange, mas somente se a política de voz aplicada à chamada especifica um número de telefone de correio de voz que é exclusivo e não inclui uma extensão tempo.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware e software para resiliência de sites de filial

Os requisitos de hardware e software variam, dependendo da solução de resiliência.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para Aparelhos de Filial Persistente

O hardware e o software necessários estão integrados ao aparelho de ramificação sobreviventes. No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter os endereços IP de clientes; caso contrário, quando a concessão de DHCP expirar, os clientes não terão conectividade IP.

Se os servidores DNS da empresa estiverem localizados somente em sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma falha de WAN e, portanto, a descoberta do Skype for Business Server que usa o SRV (registro de recurso de serviço) DNS falhará. Para garantir o redirecionamento de prompt durante uma falha de WAN, os registros DNS devem ser armazenados em cache no site da filial. Se o roteador de ramificação oferecer suporte, ative o cache de DNS. Ou você pode implantar um servidor DNS na ramificação. Isso pode ser um servidor autônomo ou uma versão do aparelho de ramificação sobreviventes que ofereça suporte a recursos de DNS. Para obter detalhes, entre em contato com seu provedor de aparelho de ramificação sobreviventes.

> [!NOTE]
> Não é necessário ter um controlador de domínio em um site de filial. O aparelho de ramificação sobreviventes autentica clientes usando um certificado especial que envia o cliente em resposta à solicitação de certificado do cliente quando ele entra.

Os clientes do Skype for Business podem descobrir o Skype for Business Server usando a opção de DHCP 120 (opção de registrador de SIP). Essa opção pode ser configurada de uma de destas duas maneiras:

- Configure o servidor DHCP no site de filial para responder a consultas DHCP 120, que retornam o FQDN do registrador na ramificação da ramificação sobreviventes ou do servidor de ramificação sobreviventes.

- Ative o DHCP do Skype for Business Server. Quando está ativado, o registrador do Skype for Business Server responde às consultas de opção de DHCP 120. Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente das Opções 120 do DHCP.

Além disso, para sites de filial maiores, com várias sub-redes, agentes de retransmissão DHCP devem ser habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).

Por fim, os usuários do site de filiais devem ser configurados para Enterprise Voice e provisionados com um ponto de extremidade de comunicação unificado apropriado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para Servidores de Filial Persistente

Os requisitos para servidores de filiais sobreviventes são os mesmos dos requisitos para um servidor front-end. Para obter mais detalhes, consulte [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos para implantações em todo o site do Skype for Business Server para toda a escala

Para obter detalhes, consulte [requisitos do servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) na documentação de planejamento.

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
| Rota Local de Redmond  <br/> | ^\+1 (425           | 206                     | 253) (\d{7}) $  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Rota Local de Dallas  <br/>  | ^\+1 (972           | 214                     | 469) (\d{7}) $  <br/>                       | Local  <br/>                                    |
| Rota Universal  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Tronco 1  <br/> Tronco 2  <br/> Tronco 3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Rota de Usuários de Dallas  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Tronco 3  <br/>                             | Dallas-GW1  <br/>                               |

Na tabela 1, um uso de telefone de GlobalPSTNHopoff é adicionado após o uso de telefone DallasUsers na Política de Chamada de Dallas. Isso permite que as chamadas com a política de chamada de Dallas usem rotas configuradas para o uso de telefone GlobalPSTNHopoff, caso uma rota para o uso do telefone DallasUsers não esteja disponível.


