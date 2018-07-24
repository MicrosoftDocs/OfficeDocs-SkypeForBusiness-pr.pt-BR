---
title: Planejar para mobilidade Skype para Business Server
ms.author: heidip
author: microsoftheidi
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planeje sua implementação de mobilidade para Skype para Business Server.
ms.openlocfilehash: 660f5013cd2e41ea08fdd2567fb9d51f58c1b8c6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003004"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planejar para mobilidade Skype para Business Server
 
Planeje sua implementação de mobilidade para Skype para Business Server.
  
Com o Skype para Business Server, você pode implantar o recurso de mobilidade para fornecer Skype para a funcionalidade do servidor de negócios em dispositivos móveis. Este artigo fornece detalhes sobre o recurso de mobilidade e ajuda a planejar sua implantação.
  
O recurso de mobilidade para Skype para Business Server é capaz de oferecer suporte a clientes móveis do Skype para a empresa, bem como os clientes do Lync voltando 2010. Depois que ele for implantado, os usuários podem se conectar ao seu Skype para implantação de servidor de negócios usando com suporte em iOS, Android e Windows Phone dispositivos móveis tirar vantagem dos vários recursos diferentes, incluindo recursos do Enterprise Voice. Incluímos uma lista parcial abaixo, e você também pode verificar a [comparação de recursos do cliente de Desktop do Skype for Business](clients-and-devices/desktop-feature-comparison.md) para obter mais informações:
  
- Enviar e receber mensagens
    
- Exibir a presença
    
- Exibir contatos
    
- Clicar para ingressar em uma conferência
    
- Telefonar via trabalho
    
- Acesso a número único
    
- Caixa postal
    
- Notificação de chamada perdida
    
- Voz sobre IP  (VoIP)
    
- Vídeo de participante (H.264)
    
- Exibir o conteúdo da reunião (PowerPoint e compartilhamento de área de trabalho/aplicativos)
    
Tudo isso é feito por meio da API Web de Comunicações Unificadas (UCWA). UCWA foi introduzida pela primeira vez no Lync Server 2013 e ainda está em uso para Skype para Business Server. Não há uma funcionalidade adicional para se comunicar com clientes do Lync 2010 e que é o serviço de mobilidade (MCX). Esses são serviços complementares, permitindo o Lync Server 2010 e clientes 2013, bem como Skype para clientes corporativos, para acessar o Skype para implantações de servidor de negócios com êxito.
  
> [!NOTE]
> Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Os usuários precisarem de atualização para um cliente atual. 
  
É importante observar que enquanto todos esses recursos estão disponíveis depois que tiver sido implementada mobilidade, eles podem funcionar um pouco diferente em alguns dispositivos. Temos um site que discute a quais recursos funcionam em quais dispositivos, em [comparação de recursos do cliente móvel para Skype para negócios](clients-and-devices/mobile-feature-comparison.md). Também temos alguns excelente dispositivo e informações do sistema operacional em [plano para clientes e dispositivos](clients-and-devices/clients-and-devices.md).
  
Mobilidade faz uso da descoberta automática recurso, que permite que os clientes localizem automaticamente Skype para serviços da web de Business Server sem precisar digitar em qualquer URLs (eles ainda não necessário conhecê-los) de usuários. Caso você precise solucionar problemas, ainda há suporte para a entrada manual de URLs.
  
As notificações por push também são suportadas para quando o Skype para o aplicativo de negócios não está em execução em segundo plano (ou para dispositivos móveis que não oferecem suporte a aplicativos em execução em segundo plano). Uma notificação de envio é enviada a um dispositivo móvel, sobre um evento que ocorre quando o aplicativo ou dispositivo está inativo. Um bom exemplo está faltando uma mensagem de mensagens Instantâneas quando sua do telefone não ativa, que possam resultar em uma notificação de envio que estão sendo enviada (Isso é apresentado como uma proposta ou notificação, como quando o aplicativo está sendo executado em segundo plano). Com notificações de push, os usuários não perca mensagens Instantâneas ou chamadas de voz.
  
Para obter mais informações, confira as seguintes seções:
  
- [Componentes de mobilidade](mobility.md#MobilityComponents)
    
- [Topologias com suporte](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Como definir seus requisitos de mobilidade](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de mobilidade
<a name="MobilityComponents"> </a>

Há quatro serviços que compõem a mobilidade para Skype para Business Server:
  
- **API Web de Comunicações Unificadas (UCWA)**
    
    Fornece serviços de comunicação em tempo real com o mobile e clientes da web para o Skype para Business Server. Quando for implantado Skype para Business Server, do diretório virtual um UCWA criado nos serviços web internos e externos. Um componente virtual nesse diretório virtual aceita chamadas de clientes habilitados para UCWA. Os aplicativos cliente se comunicam por meio de uma interface REST (transferência de estado representacional) para:
    
  - presença
    
  - contatos
    
  - IM (sistema de mensagens instantâneas)
    
  - VoIP
    
  - videoconferências
    
  - colaboração
    
    O UCWA utiliza um canal baseado em P-GET para enviar eventos, como uma chamada de entrada, uma mensagem instantânea de entrada ou uma mensagem para o aplicativo cliente.
    
- **Serviço de Mobilidade (MCX)**
    
    Suporta Skype para a funcionalidade do servidor de negócios, como mensagens Instantâneas, presença e contatos, em dispositivos móveis. O serviço de mobilidade está instalado em cada servidor Front-End em cada pool que tenha destinado ao suporte Skype para a funcionalidade do servidor de negócios em dispositivos móveis. Quando você instala o Skype para Business Server 2015 um novo diretório virtual (Mcx) é criado sob os sites internos e externos em seus servidores Front-End.
    
    > [!NOTE]
    > Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Os usuários precisarem de atualização para um cliente atual.
  
- **Serviço de Descoberta Automática**
    
    Identifica a localização do usuário e permite que dispositivos móveis e outro Skype para clientes corporativos localizar recursos (por exemplo, as URLS internas e externas do Skype para Business Server Web Services, a URL Mcx ou UCWA URL), independentemente do local de rede. A descoberta automática usa nomes de host codificados (lyncdiscoverinternal para usuários da rede e lyncdiscover para usuários fora da rede) e o domínio SIP do usuário. Ela dá suporte a conexões de clientes que usam HTTP ou HTTPS. 
    
    O serviço Descoberta automática é instalado em cada servidor Front-End e em cada diretor em cada pool que tenha destinado ao suporte Skype para a funcionalidade do servidor de negócios em dispositivos móveis. Quando você instala o serviço, um novo diretório virtual (descoberta automática) é criado sob os sites internos e externos em seus servidores Front-End e diretores.
    
- **Serviço de notificação por push**
    
    Um serviço baseado em nuvem que está localizado em sua Skype para data center Business Online. Telefones que não têm Skype para clientes corporativos em execução em segundo plano, quando um novo evento acontece, notificação de um evento perdida (chamado de uma notificação de push) é enviada para o dispositivo móvel em vez disso. O serviço de mobilidade envia uma notificação para o serviço de notificação de push (MPNS), que envia para o dispositivo móvel. O usuário pode então responder à notificação em seu dispositivo móvel para ativar o aplicativo. Um servidor de borda é necessário para essa funcionalidade.
    
## <a name="supported-topologies"></a>Topologias suportadas
<a name="SupportedTopos"> </a>

Temos o seguinte Skype com suporte para aplicativos de servidor de negócios para o planejamento de topologia:
  
- Mobilidade Standard Edition
    
- Mobilidade Enterprise Edition
    
Você deve ser capaz de usar essa funcionalidade com Skype para servidores de borda do servidor de negócios ou servidores de borda do Lync Server 2013.
  
O serviço de mobilidade é suportado nos servidores Front-End quando colocado com a função de servidor de mediação, com duas interfaces de rede, mas você deve realizar as etapas apropriadas para configurar as interfaces. Você precisará atribuir endereços IP para a interface específica que comunicarão como o servidor de mediação e a interface de IP de rede que se comunicarão como servidor Front-End. Você pode fazer isso no construtor de topologia, selecionando o endereço IP correto para cada serviço, em vez de usar a seleção de **usar todos os endereços IP configurados** padrão.
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

É importante planejar os vários cenários de aplicativos móveis que os usuários móveis podem encontrar. Por exemplo, alguém pode começar a usar um aplicativo móvel fora do trabalho conectando-se por meio de uma rede 3G e depois mudar para a rede Wi-Fi corporativa ao chegar ao trabalho. Eles podem alternar para 4G ao sair de sua construção. Planeje agora para poder dar suporte a essas transições de rede e garantir uma experiência do usuário consistente.
  
### <a name="dns-configuration"></a>Configuração de DNS

Os serviços de mobilidade Mcx e UCWA usam o DNS da mesma maneira. Com a Descoberta Automática, os dispositivos móveis usam DNS para localizar recursos. Durante a pesquisa de DNS, é feita uma tentativa de conexão com o FQDN que está associado ao registro DNS interno (lyncdiscoverinternal.[nome de domínio interno]). Se o registro DNS interno não puder ser usado para estabelecer essa conexão, será feita uma segunda tentativa de conexão, dessa vez com o registro DNS externo (lyncdiscover.[sipdomain]). Então, por que há dois? Um dispositivo móvel que é interno à sua rede poderá usar a URL de Descoberta Automática interna. Dispositivos móveis externos usarão a URL de Descoberta Automática externa. Em ambos os casos, o serviço Descoberta automática retornará todas as URLs de serviço Web para o pool primário do usuário, que inclui o serviço de mobilidade (Mcx e UCWA).
  
Espera-se que as solicitações de descoberta automática externas serão encaminhadas através do proxy reverso que você configurou para Skype para Business Server. No entanto, a URL interna do serviço de mobilidade e a URL externa do serviço de mobilidade estão associadas com o FQDN de serviços Web externos. Portanto, independentemente se um dispositivo móvel é interno ou externo à sua rede, o dispositivo sempre se conecta ao Skype para serviço de mobilidade de servidor de negócios externamente, por meio do proxy reverso.
  
> [!NOTE]
> Conforme observado apenas, todo tráfego de serviço de mobilidade (interno e externo) serão encaminhadas através do proxy reverso. Porém, às vezes, surge um problema quando o tráfego interno sai por uma interface, para depois tentar voltar pela mesma interface. Isso pode violar suas regras de segurança contra falsificação (formalmente, isso é chamado de falsificação de pacote TCP). Você precisará permitir que a **Forma de fixação** ter a função de mobilidade.
  
> [!NOTE]
> Se você estiver pronto para fazer isso, você também pode optar por usar um proxy reverso separado do seu firewall (para fins, prevenção de falsificação sempre devem ser impostas no seu firewall de segurança). Dessa forma, o hairpin pode acontecer na interface externa do proxy reverso, em vez de interface externa do seu firewall. Isso permite que você detectar a falsificação corretamente no seu firewall enquanto você fique tranquilo a regra em seu proxy reverso, e você obter sua funcionalidade de mobilidade. 
  
> [!NOTE]
> Se você passar essa rota, certifique-se de usar o host DNS ou os registros CNAME para definir o proxy reverso para o comportamento de hairpin (e não o firewall), se possível. 
  
Há alguns itens que você precisa configurar para dar suporte aos usuários dentro e fora da rede corporativa.
  
Estas são as regras para FQDNs Web internos e externos:
  
- Novos registros DNS CNAME ou A (host, se IPv6, AAAA), para descoberta automática.
    
- Nova regra de firewall, se você quiser dar suporte a notificações de envio pela sua rede Wi-Fi.
    
- Assuntos nomes alternativos nos certificados de servidor interno e certificados de proxy reverso para descoberta automática.
    
- Afinidade de origem de alterações de configuração de balanceamento de carga de hardware do Front End Server.
    
Estes são os requisitos de topologia necessários para suportar o Mobility Service and Autodiscover Service:
  
- O Front-End FQDN interno da web deve ser distinto a Front End pool FQDN da web externo.
    
- O FQDN interno da Web só deve ser resolvido para a rede corporativa e ser acessível nela.
    
- O FQDN interno da Web só deve ser resolvido para a Internet e ser acessível nela.
    
- Para um usuário dentro da rede corporativa, a URL do serviço de mobilidade deve ser tratada para o FQDN da web externo. Esse requisito é para o serviço de mobilidade e só se aplica a essa URL.
    
- Para um usuário fora da rede corporativa, a solicitação deve ir ao FQDN do pool de Front-End ou diretor externos da web.
    
Se você dá suporte à descoberta automática, precisa criar os seguintes registros DNS para cada domínio SIP:
  
- Um registro DNS interno para dar suporte a usuários móveis que se conectam da rede de sua organização
    
- Um registro DNS externo ou público para dar suporte a usuários móveis que se conectam pela Internet.
    
A URL de descoberta automática interna não deve ser endereçável de fora da rede interna. A URL de descoberta automática externa não deve ser endereçável de dentro da rede. Porém, se isso não for possível para a URL externa, sua funcionalidade de cliente móvel provavelmente não será afetada, pois a URL interna será sempre tentada primeiro.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de Firewall e de Porta

Abordamos a maioria desses procedimentos em nossa outras documentações, mas especificamente para mobilidade, você vai querer ter as seguintes portas abertas em sua rede corporativa Wi-Fi, se você tiver quaisquer usuários hospedados em um aparelho de filial persistente (SBA):
  
- UcwaSipExternalListeningPort requer 5088.
    
- UcwaSipPrimaryListeningPort requer 5089.
    
### <a name="certificate-requirements"></a>Requisitos de certificado

Se você estiver usando a descoberta automática para sua Skype para clientes móveis de negócios, você precisará modificar as listas de SAN (nome alternativo da entidade) em seus certificados para oferecer suporte a conexões seguras de seus clientes móveis. Se já tiver certificados, você precisará solicitar e atribuir novos certificados com as entradas SAN descritas aqui. Isso precisará ser feita para cada servidor Front-End e diretor (se estiver no seu ambiente) que executa o serviço de descoberta automática. Também recomendamos modificando a que lista de SAN em seus certificados de proxy reverso, a adição de entradas de SAN para cada domínio SIP em sua organização.
  
Este deve ser um processo simples, se você está solicitando os novos certificados desativa uma autoridade de certificação interna (autoridade de certificação), mas os certificados públicos são mais complexa e muito mais caros solicitar novamente, para não mencionar pode ser dispendiosa adicionar muita SIP domínios para um novo cert pública. Nessa situação, há uma abordagem que é suportada, mas **não recomendado**. Você pode configurar o proxy reverso para tornar a solicitação de serviço de descoberta automática inicial sobre a porta 80, que usará o HTTP, em vez da porta 443, que é HTTPS (e 443 é a configuração padrão). Essa entrada solicitação será redirecionada para a porta 8080 no seu pool de Front-End ou diretor. Fazendo isso, você não precisará fazer alterações nos certificados, pois esse tráfego não usa HTTPS para solicitações. Porém, novamente, não recomendamos isso, embora funcione para você.
  
### <a name="windows-and-iis-requirements"></a>Requisitos do Windows e do IIS

Você deve ter uma versão com suporte do Windows Server para sua Skype para ambiente de servidor de negócios. Como resultado, também deve ter o IIS 8 ou o IIS 8.5 para suas necessidades de mobilidade. Será necessário haver algumas alterações às configurações ASP.NET padrão, mas o instalador do serviço de mobilidade que fará automaticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Se você estiver usando uma topologia para Skype para servidor de negócios que inclui um HLB para o pool de Front-End (que seria qualquer topologia que inclui mais de um servidor Front-End), o externo dos serviços Web IPs virtuais (VIPs) para tráfego de serviços da Web precisam ser configurados para a fonte. A afinidade da origem garante que várias conexões de um único cliente sejam enviadas ao mesmo servidor para manter o estado da sessão.
  
Se você pretende suportar Skype para clientes móveis do Business somente através da rede de Wi-Fi interna, você deve configurar seu VIPs de serviços Web internos para a fonte como descrito VIPs de serviços Web externos. Nessa situação, você deve usar source_addr (ou TCP) afinidade para VIPs no HLB serviços Web internos.
  
Para obter detalhes sobre esse, revise a documentação de [requisitos para Skype para negócios de balanceamento de carga](network-requirements/load-balancing.md) .
  
### <a name="reverse-proxy-requirements"></a>Requisitos de proxy reverso

Para suportar a descoberta automática para Skype para clientes móveis de negócios, você precisará atualizar a regra de publicação atual da seguinte maneira:
  
- Se você decidir atualizar listas de SAN em seus certificados de proxy reverso e você estiver usando o HTTPS para a solicitação de serviço de descoberta automática inicial, você precisa atualizar a regra de publicação na web para lyncdiscover. \<sipdomain\>. Normalmente, isso é combinado com a regra de publicação para a URL externa de serviços Web no pool de Front-End.
    
- Se você tiver decidido usar HTTP para a solicitação inicial de serviço de descoberta automática evitar a atualizar SAN listam para seus certificados de proxy reverso (que não é recomendável), você precisará criar uma nova regra de publicação na web para a porta 80 HTTP/TCP, se não houver um já. Se essa regra existir, atualize-o para incluir um lyncdiscover. \<sipdomain\> entrada.
    
## <a name="defining-your-mobility-needs"></a>Como definir seus requisitos de mobilidade
<a name="MobilityNeeds"> </a>

Agora que já analisamos as topologias, os componentes e os requisitos técnicos, vamos examinar o que sua organização pode precisar em termos de uma implementação de mobilidade.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Você deseja usar a descoberta automática para clientes móveis do Skype for Business?

É altamente recomendável que você use a descoberta automática. Ela exigirá a criação de novos registros DNS internos e externos, conforme documentado na seção Requisitos técnicos acima. Com a descoberta automática, o Skype para clientes corporativos pode localizar automaticamente Skype para serviços corporativos de Web Server de qualquer local, sem a necessidade de uma URL a ser inserido manualmente.
  
Você poderá usar as configurações manuais, se precisar. Estas URLs precisarão ser inseridas pelos usuários em seus dispositivos móveis:
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** para acesso externo.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** para acesso interno.
    
Mais uma vez, recomendamos o uso da descoberta automática. As configurações manuais podem ser úteis para solucionar problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>Você dará suporte a notificações por push?

As notificações por push são usadas para aplicativos móveis compatíveis com essa funcionalidade para notificar usuários da ocorrência de eventos enquanto o aplicativo não está ativo. Seu servidor de borda será necessário ter uma relação de federação com sua Skype baseado em nuvem para negócios Push notificação de serviço do servidor, que se encontra no Skype para o datacenter Business Online. Você precisará executar um cmdlet para habilitar notificações por push.
  
> [!NOTE]
> Se você tiver qualquer pessoa ainda usando clientes do Lync Server 2010, eles precisará abrir de porta 5223 TCP saída em sua rede de WiFi do enterprise. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Você deseja que todos os seus usuários acessar todos os recursos de mobilidade, ou você deseja especificar os usuários que podem acessar esses recursos em vez disso?

Temos uma tabela para ajudá-lo com alguns dos recursos que estão disponíveis para todos os usuários e se eles estiver definidos que maneira ou não por padrão. Para obter uma lista completa, examine o [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Os escopos para todos esses recursos são Global/Site/Usuário. 
  
|**Recurso**|**Nome do parâmetro**|**Descrição**|**Configuração padrão**|
|:-----|:-----|:-----|:-----|
|Habilitar mobilidade  <br/> |EnableMobility  <br/> |Usuários de controles em um determinado escopo com Skype para o cliente móvel de negócios instalado. Se a política for definida como False, os usuários não poderão entrar no serviço com o cliente.  <br/> |True  <br/> |
|Voz Externa  <br/> |EnableOutsideVoice  <br/> |Habilita o usuário a utilizar Telefonar via Trabalho. Esse recurso permite enviar e receber chamadas usando o número comercial em vez do número do celular. Se essa configuração for definida como False, os usuários não poderão fazer nem receber chamadas no celular ao usar o número de telefone comercial.  <br/> |True  <br/> |
|Habilitar áudio e vídeo por IP  <br/> |EnableIPAudioVideo  <br/> |Quando definida como padrão, essa configuração permite que um usuário utilize VoIP para fazer ou receber chamadas telefônicas ou chamadas de vídeo em seu dispositivo móvel. Quando essa configuração é definida como False, os usuários não podem usar seus dispositivos móveis para realizar essas ações.  <br/> |True  <br/> |
|Requer WiFi para áudio por IP  <br/> |RequireWiFiForIPAudio  <br/> |Define se um cliente precisará fazer e receber chamadas por VoIP sobre Wi-Fi, em vez de uma rede de dados celular. Se essa configuração for definida como True, os usuários só poderão fazer e receber chamadas por VoIP quando estiverem conectados via Wi-Fi.  <br/> |False  <br/> |
|Requer WiFi para vídeo por IP  <br/> |RequireWiFiForIPVideo  <br/> |Define se um cliente precisará fazer e receber chamadas de vídeo por Wi-Fi, em vez de uma rede de dados celular. Se essa configuração for definida como True, os usuários só poderão fazer e receber chamadas por VoIP quando estiverem conectados via Wi-Fi.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Os usuários que não estão habilitados para Enterprise Voice podem usar Clique para Ingressar para ingressar em conferências?

Para os usuários tenham acesso aos recursos de mobilidade e telefonar via trabalho, eles precisam estar habilitadas para o Enterprise Voice. Porém, mesmo se não estiverem habilitados, eles ainda poderão participar de conferências clicando em um link em seu dispositivo móvel, mas apenas se tiverem uma política de voz apropriada atribuída a eles. Você pode:
  
- atribuir uma política de voz específica a esses usuários ou
    
- garantir que exista uma política global ou uma política de nível de site e que ela se aplique a eles.
    
De qualquer forma, a política de voz que você atribuir precisará ter registros de uso de PSTN (rede telefônica pública comutada) e rotas que definirão para onde os usuários poderão discar para ingressar em conferências.
  
> [!NOTE]
> Os usuários móveis que deseja usar o recurso Clique para ingressar exigem uma política de voz, juntamente com os registros relacionados de uso PSTN e rotas de voz, porque quando eles clicam no link em seus dispositivos móveis, uma chamada de saída do Skype para Business Server será o resultado. 
  

