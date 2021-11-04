---
title: Planejar mobilidade para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planeje sua implementação do Mobility para Skype for Business Server.
ms.openlocfilehash: 5d78739be230c7c68157d8bae474bf63133a96d7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746707"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planejar mobilidade para Skype for Business Server
 
Planeje sua implementação do Mobility para Skype for Business Server.
  
Com Skype for Business Server, você pode implantar o recurso Mobility para fornecer Skype for Business Server funcionalidade em dispositivos móveis. Este artigo fornece detalhes sobre o recurso Mobility e ajuda você a planejar sua implantação.
  
O recurso Mobility para Skype for Business Server é capaz de dar suporte a clientes móveis para Skype for Business, bem como clientes do Lync voltando para 2010. Depois que ele é implantado, os usuários podem se conectar à sua implantação Skype for Business Server usando dispositivos móveis iOS, Android e Windows Phone compatíveis para tirar proveito de vários recursos diferentes, incluindo Enterprise Voice recursos. Incluímos uma lista parcial abaixo e você também pode verificar a comparação de recursos do cliente da área de trabalho Skype for Business [mais](clients-and-devices/desktop-feature-comparison.md) informações:
  
- Enviar e receber mensagens
    
- Exibir presença
    
- Exibir contatos
    
- Clique para participar de uma conferência
    
- Chamada via trabalho
    
- Alcance de número único
    
- Caixa postal
    
- Notificação de chamada perdida
    
- Voice over IP (VoIP)
    
- Vídeo do participante (H.264)
    
- Exibindo conteúdo de reunião (PowerPoint e compartilhamento de área de trabalho/aplicativo)
    
Tudo isso é realizado por meio da API Web de Comunicações Unificadas ou UCWA. O UCWA foi introduzido pela primeira vez no Lync Server 2013 e ainda está em uso para Skype for Business Server. Há uma funcionalidade adicional para se comunicar com clientes do Lync 2010, e esse é o Mobility Service (MCX). Esses são serviços complementares, permitindo que clientes do Lync Server 2010 e 2013, bem como clientes Skype for Business, acessem implantações Skype for Business Server com êxito.
  
> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
É importante observar que, embora todos esses recursos estão disponíveis depois que o Mobility foi implementado, eles podem funcionar de forma um pouco diferente em alguns dispositivos. Temos um site que discute quais recursos funcionam em quais dispositivos, na comparação de recursos do cliente [móvel para Skype for Business](clients-and-devices/mobile-feature-comparison.md). Também temos algumas informações excelentes sobre dispositivos e sistema operacional em [Plan for clients and devices](clients-and-devices/clients-and-devices.md).
  
A mobilidade usa o recurso Descoberta Automática, que permite que os clientes localizem automaticamente os serviços Web Skype for Business Server sem que os usuários precisem inserir urls (eles nem precisarão os conhecer). Se você precisar solucionar problemas, a entrada manual de URLs ainda será suportada.
  
Também há suporte para notificações por push, para quando o aplicativo Skype for Business não está em execução em segundo plano (ou para dispositivos móveis que não suportam aplicativos em execução em segundo plano). Uma notificação por push é enviada a um dispositivo móvel sobre um evento que ocorre quando o dispositivo ou aplicativo está inativo. Um bom exemplo é a falta de uma mensagem de IM quando o telefone não está ativo, o que resultaria em uma notificação por push sendo enviada (isso é apresentado como uma notificação ou notificação, como quando o aplicativo está em execução em segundo plano). Com notificações por push, os usuários não perderão chamadas de voz ou mensagens de voz.
  
Para obter mais informações, temos as seguintes seções:
  
- [Componentes de mobilidade](mobility.md#MobilityComponents)
    
- [Topologias com suporte](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Definindo suas necessidades de mobilidade](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de mobilidade
<a name="MobilityComponents"> </a>

Há quatro serviços que incluem o Mobility para Skype for Business Server:
  
- **Unified Communications Web API (UCWA)**
    
    Fornece serviços para comunicações em tempo real com clientes móveis e web para Skype for Business Server. Quando Skype for Business Server é implantado, um diretório virtual do UCWA é criado nos serviços Web internos e externos. Um componente virtual neste diretório virtual que aceita chamadas de clientes habilitados para UCWA. Os aplicativos cliente se comunicam por meio de uma interface REST (transferência de estado representacional) para:
    
  - presença
    
  - contacts
    
  - mensagens instantâneas (IM)
    
  - VoIP
    
  - videoconferência
    
  - colaboração
    
    O UCWA usa um canal baseado em P-GET para enviar eventos, como uma chamada de entrada, um IM de entrada ou uma mensagem para o aplicativo cliente.
    
- **Serviço de mobilidade (MCX)**
    
    Oferece Skype for Business Server funcionalidade, como IM, presença e contatos, em dispositivos móveis. O serviço Mobility é instalado em todos os Servidores Front-End em cada pool que se destina a dar suporte Skype for Business Server funcionalidade em dispositivos móveis. Quando você instala o Skype for Business Server 2015, um novo diretório virtual (Mcx) é criado em sites internos e externos em seus Servidores Front-End.
    
    > [!NOTE]
    > O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
- **Serviço de descoberta automática**
    
    Identifica a localização do usuário e permite que dispositivos móveis e outros clientes Skype for Business localizem recursos (como ASLLs internas e externas para serviços Web do Skype for Business Server, a URL mcx ou a URL do UCWA) independentemente do local da rede. A descoberta automática usa nomes de host hardcoded (lyncdiscoverinternal para usuários dentro da rede, lyncdiscover para usuários fora da rede) e o domínio SIP do usuário. Ele dá suporte a conexões de cliente que usam HTTP ou HTTPS. 
    
    O serviço descoberta automática é instalado em todos os Servidores Front-End e em todos os Diretores em cada pool que se destinam a dar suporte Skype for Business Server funcionalidade em dispositivos móveis. Quando você instala o serviço, um novo diretório virtual (Descoberta Automática) é criado em sites internos e externos em seus Servidores e Diretores front-end.
    
- **Serviço de notificação por push**
    
    Um serviço baseado em nuvem localizado em seu data center Skype for Business Online. Em telefones que não têm um cliente Skype for Business em segundo plano, quando um novo evento acontece, a notificação de um evento perdido (chamada de notificação por push) é enviada ao dispositivo móvel. O serviço Mobility envia uma notificação para o serviço de notificação por push (MPNS), que a envia para o dispositivo móvel. Em seguida, o usuário pode responder à notificação em seu dispositivo móvel para ativar o aplicativo. Um Servidor de Borda é necessário para essa funcionalidade.
    
## <a name="supported-topologies"></a>Topologias suportadas
<a name="SupportedTopos"> </a>

Temos os seguintes aplicativos de Skype for Business Server para seu planejamento de topologia:
  
- Mobilidade Edição Standard
    
- Mobilidade Edição Enterprise
    
Você deve ser capaz de usar essa funcionalidade com servidores Skype for Business Server de Borda ou Servidores de Borda do Lync Server 2013.
  
O serviço mobility é suportado em Servidores Front-End quando alocado com a função servidor de mediação, com duas interfaces de rede, mas você precisa tomar as etapas apropriadas para configurar essas interfaces. Você precisará atribuir endereços IP à interface específica que se comunicará como o Servidor de Mediação e à interface IP de rede que se comunicará como o Servidor front-end. Você pode fazer isso no Construtor de Topologia selecionando o endereço IP correto para cada serviço, em vez de usar a seleção padrão **Usar todos os endereços IP configurados.**
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

É importante planejar os vários cenários de aplicativo móvel que seus usuários móveis podem encontrar. Por exemplo, alguém pode começar a usar um aplicativo móvel fora do trabalho conectando-se por meio de uma rede 3G e alternar para a rede corporativa Wi-Fi quando chegar ao trabalho. Eles podem alternar para 4G ao sair de seu edifício. O planejamento agora permitirá que você suporte essas transições de rede e garanta uma experiência de usuário consistente.
  
### <a name="dns-configuration"></a>Configuração de DNS

Os serviços mobility Mcx e UCWA usam DNS da mesma maneira. Com a Descoberta Automática, os dispositivos móveis usam o DNS para localizar recursos. Durante a análise dns, uma conexão tentou com o FQDN que está associado ao registro DNS interno (lyncdiscoverinternal.[ nome de domínio interno]). Se o registro DNS interno não puder ser usado para fazer essa conexão, uma segunda conexão será tentada, desta vez para o registro DNS externo (lyncdiscover.[ sipdomain]). Então, por que ter dois? Um dispositivo móvel interno à sua rede poderá usar a URL de Descoberta Automática interna. Dispositivos móveis externos usarão a URL de Descoberta Automática externa. Em ambos os casos, o serviço de Descoberta Automática retornará todas as URLs do serviço Web para o pool 1 do usuário, que inclui o serviço mobility (Mcx e UCWA).
  
É esperado que as solicitações de Descoberta Automática externas passarão pelo proxy reverso que você configurou para Skype for Business Server. No entanto, tanto a URL do serviço de Mobilidade interna quanto a URL do serviço de Mobilidade externa estão associadas ao FQDN de Serviços Web externos. Portanto, independentemente de um dispositivo móvel ser interno ou externo à sua rede, o dispositivo sempre se conecta ao serviço Skype for Business Server Mobility externamente, por meio do proxy reverso.
  
> [!NOTE]
> Como vimos, todo o tráfego de serviço mobility (interno e externo) passará pelo proxy reverso. Mas, às vezes, surge um problema quando o tráfego interno sai por uma interface, apenas para tentar voltar na mesma interface. Isso pode violar suas regras de segurança de spoofing (formalmente chamada de spoofing de pacotes TCP). Você precisará permitir que o **Hair Pinning** tenha a função Mobility.
  
> [!NOTE]
> Se você estiver pronto para fazer isso, você também pode optar por usar um proxy reverso separado do firewall (para fins de segurança, a prevenção de spoofing sempre deve ser imposta no firewall). Dessa forma, o hairpin pode acontecer na interface externa do proxy reverso, em vez da interface externa do firewall. Isso permite que você detecte a fraude corretamente no firewall enquanto você descontrai a regra no proxy reverso e recebe sua funcionalidade mobility. 
  
> [!NOTE]
> Se você seguir essa rota, use os registros de host DNS ou CNAME para definir o proxy reverso para o comportamento do hairpin (não o firewall), se possível. 
  
Há algumas coisas que você precisará configurar para dar suporte a usuários dentro e fora da sua rede corporativa.
  
Estas são as regras para FQDNs da Web internas e externas:
  
- Novo CNAME ou A (host, se IPv6, AAAA) registros DNS, para descoberta automática.
    
- Nova regra de firewall, se você quiser dar suporte a notificações por push por meio de sua Wi-Fi rede.
    
- Nomes alternativos de assunto em certificados de servidor internos e certificados de proxy reverso, para descoberta automática.
    
- A configuração balanceada de carga de hardware do Servidor front-end altera a afinidade de origem.
    
Estes são os requisitos de topologia necessários para dar suporte ao Serviço de Mobilidade e Ao Serviço de Descoberta Automática:
  
- O FQDN da Web interno do pool front-end deve ser distinto do FQDN da Web externo do pool de Front-End.
    
- O FQDN da Web interno só deve ser resolvido e acessível de dentro da rede corporativa.
    
- O FQDN da Web externo só deve resolver e ser acessível da Internet.
    
- Para um usuário dentro da rede corporativa, a URL do serviço mobility deve ser endereçada ao FQDN da Web externo. Esse requisito é para o serviço mobility e se aplica somente a essa URL.
    
- Para um usuário fora da rede corporativa, a solicitação deve ir para o FQDN da Web externo do pool de Front-End ou Diretor.
    
Se você suportar a descoberta automática, precisará fazer os seguintes registros DNS para cada domínio SIP:
  
- Um registro DNS interno para dar suporte a usuários móveis que se conectam de dentro da rede da sua organização.
    
- Um registro DNS externo ou público para dar suporte a usuários móveis que se conectam da Internet.
    
A URL de descoberta automática interna não deve ser abordada de fora da rede interna. A URL de descoberta automática externa não deve ser abordada de dentro da rede. Mas se isso não for possível para a URL externa, a funcionalidade do cliente móvel provavelmente não será afetada, pois a URL interna sempre será tentada primeiro.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de porta e firewall

Abordamos a maior parte disso em nossa outra documentação, mas especificamente para Mobility, você vai querer abrir as seguintes portas em sua rede corporativa Wi-Fi se você tiver algum usuário em um Dispositivo de Filial Desavivável (SBA):
  
- UcwaSipExternalListeningPort requer 5088.
    
- UcwaSipPrimaryListeningPort requer 5089.
    
### <a name="certificate-requirements"></a>Requisitos de Certificação

Se você estiver usando a descoberta automática para seus clientes móveis Skype for Business, será necessário modificar as listas SAN (nome alternativo de assunto) em seus certificados para dar suporte a conexões seguras de seus clientes móveis. Se você já tiver certificados no local, precisará solicitar e atribuir novos certificados com as entradas SAN descritas aqui. Isso precisará ser feito para cada Servidor e Diretor front-end (se em seu ambiente) que executa o serviço de Descoberta Automática. Também recomendamos modificar as listas SAN em seus certificados de proxy reverso, adicionando entradas SAN para cada domínio SIP em sua organização.
  
Esse deve ser um processo simples se você estiver solicitando os novos certificados de uma autoridade de certificação interna (autoridade de certificação), mas os certificados públicos são mais complexos e potencialmente muito mais caros para a nova solicitação, sem mencionar que pode ser caro adicionar muitos domínios SIP a um novo certificado público. Nessa situação, há uma abordagem com suporte, mas **não recomendada.** Você pode configurar seu proxy reverso para fazer a solicitação inicial de serviço de Descoberta Automática pela porta 80, que usará HTTP, em vez da porta 443, que é HTTPS (e 443 é a configuração padrão). Essa solicitação de entrada será redirecionada para a porta 8080 em seu pool de Front-End ou Diretor. Ao fazer isso, você não precisará fazer alterações de certificado, pois esse tráfego não está usando HTTPS para solicitações. Mas, novamente, não recomendamos isso, embora funcione para você.
  
### <a name="windows-and-iis-requirements"></a>Windows e requisitos do IIS

Você deve ter uma versão do Windows Server com suporte para seu ambiente Skype for Business Server ambiente. Como resultado, você também deve ter o IIS 8 ou o IIS 8.5 para suas necessidades de mobilidade. Haverá algumas alterações nas configurações de ASP.NET padrão, mas o instalador do serviço mobility fará isso automaticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Se você estiver usando uma topologia para Skype for Business Server que inclui um HLB para seu pool de Front-End (que seria qualquer topologia que inclua mais de um Servidor Front-End), os VIPs (IPs virtuais) externos dos Serviços Web para o tráfego de Serviços Web precisam ser configurados para origem. A afinidade de origem ajuda a garantir que várias conexões de um único cliente sejam enviadas para o mesmo servidor para manter o estado da sessão.
  
Se você planeja dar suporte Skype for Business clientes móveis somente pela sua rede interna Wi-Fi, configure seus VIPs de Serviços Web internos para origem, conforme descrito para VIPs de Serviços Web externos. Nessa situação, você deve usar source_addr afinidade (ou TCP) para os VIPs de Serviços Web internos no HLB.
  
Para obter detalhes sobre tudo isso, consulte os requisitos de [balanceamento](network-requirements/load-balancing.md) de carga para Skype for Business documentação.
  
### <a name="reverse-proxy-requirements"></a>Requisitos de Proxy Reverso

Para dar suporte à descoberta automática para Skype for Business clientes móveis, você precisará atualizar a regra de publicação atual da seguinte forma:
  
- Se você decidir atualizar as listas SAN em seus certificados de proxy reverso e estiver usando HTTPS para a solicitação inicial de serviço de Descoberta Automática, será necessário atualizar a regra de publicação da Web para lyncdiscover. \<sipdomain\> . Normalmente, isso é combinado com o rul de publicação para a URL externa dos Serviços Web no pool de Front-End.
    
- Se você decidiu usar HTTP para a solicitação inicial de serviço de Descoberta Automática para evitar a necessidade de atualizar a lista SAN para seus certificados de proxy reverso (o que não recomendamos), você precisará criar uma nova regra de publicação da Web para a porta HTTP/TCP 80, se ainda não houver uma. Se essa regra existir, atualize-a para incluir uma descoberta lyncdiscover.\<sipdomain\> entry.
    
## <a name="defining-your-mobility-needs"></a>Definindo suas necessidades de mobilidade
<a name="MobilityNeeds"> </a>

Agora que revisemos as topologias, componentes e requisitos técnicos, vamos analisar o que sua organização pode precisar em termos de implementação do Mobility.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Deseja usar a descoberta automática para clientes Skype for Business móveis?

Recomendamos que você use a descoberta automática. Ele exigirá a criação de novos registros DNS internos e externos, conforme documentado na seção Requisitos Técnicos acima. Com a descoberta automática, os clientes Skype for Business podem localizar automaticamente Skype for Business Server Web Services de qualquer local, sem precisar de uma URL para ser inserida manualmente.
  
Você pode usar configurações manuais se precisar. Essas URLs precisarão ser inseridas pelos usuários em seus dispositivos móveis:
  
- **https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** para acesso externo.
    
- **https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** para acesso interno.
    
Novamente, recomendamos o uso de descoberta automática. Você pode encontrar configurações manuais úteis para fins de solução de problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>Você vai dar suporte a notificações por push?

As notificações por push são usadas para aplicativos móveis que suportam essa funcionalidade para notificar um usuário de eventos enquanto o aplicativo não está ativo. Seu Servidor de Borda precisará ter uma relação de federação com seu Serviço de Notificação por Push baseado em nuvem Skype for Business Server, que é encontrado no datacenter Skype for Business Online. Você precisará executar um cmdlet para habilitar notificações por push.
  
> [!NOTE]
> Se você ainda tiver alguém usando clientes do Lync Server 2010, eles precisarão da porta TCP 5223 de saída aberta em sua rede WiFi corporativa. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Você deseja que todos os usuários acessem todos os recursos do Mobility ou especifique os usuários que podem acessar esses recursos?

Temos uma tabela para ajudar com alguns dos recursos que estão disponíveis para todos os usuários e se eles estão definidos dessa forma ou não por padrão. Para ver uma lista completa, confira [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Os escopos de todos esses recursos são Global/Site/User. 
  
|**Característica**|**Nome do Parâmetro**|**Descrição**|**Configuração Padrão**|
|:-----|:-----|:-----|:-----|
|Habilitar Mobilidade  <br/> |EnableMobility  <br/> |Controla os usuários em um determinado escopo que Skype for Business cliente móvel instalado. Se a política for definida como False, os usuários não poderão entrar com o cliente.  <br/> |Verdadeiro  <br/> |
|Outside Voice  <br/> |EnableOutsideVoice  <br/> |Permite que um usuário use Call Via Work, que permite que os usuários enviem e recebam chamadas usando seu número de trabalho em vez de seu número móvel. Se estiver definido como False, os usuários não poderão fazer ou receber chamadas no celular ao usar o número de telefone do trabalho.  <br/> |Verdadeiro  <br/> |
|Habilitar áudio e vídeo IP  <br/> |EnableIPAudioVideo  <br/> |De acordo com o padrão, ele permite que um usuário use VoIP para fazer ou receber chamadas de telefone ou vídeo em seu dispositivo móvel. Quando definido como False, os usuários não poderão usar seus dispositivos móveis para fazer uma dessas coisas.  <br/> |Verdadeiro  <br/> |
|Exigir WiFi para áudio IP  <br/> |RequireWiFiForIPAudio  <br/> |Define se um cliente precisará fazer e receber chamadas por VoIP no WiFi em vez de uma rede de dados celular. Se estiver definido como True, seus usuários só poderão fazer e receber chamadas VoIP quando eles estão conectados via WiFi.  <br/> |Falso  <br/> |
|Exigir WiFi para vídeo IP  <br/> |RequireWiFiForIPVideo  <br/> |Define se um cliente precisará fazer e receber chamadas de vídeo em WiFi em vez de uma rede de dados celular. Se estiver definido como True, seus usuários só poderão fazer e receber chamadas VoIP quando eles estão conectados via WiFi.  <br/> |Falso  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Os usuários que não estão habilitados para Enterprise Voice podem usar Clique para ingressar em conferências?

Para que os usuários tenham acesso a recursos de Mobilidade e Chamada via Trabalho, eles precisam estar habilitados para Enterprise Voice. Mas, mesmo que eles não sejam habilitados, eles ainda podem participar de conferências clicando em um link em seu dispositivo móvel, mas somente se eles têm uma política de Voz apropriada atribuída a elas. Você pode:
  
- atribuir uma política de Voz específica a esses usuários ou,
    
- certifique-se de que exista uma política global ou de nível de site e se aplique a elas.
    
De qualquer forma, a política de voz que você atribui precisa ter registros de uso de PSTN (rede telefônica pública comutado) e rotas que definirão onde seus usuários poderão discar para participar de conferências.
  
> [!NOTE]
> Os usuários móveis que querem usar Clique para Ingressar exigem uma política de Voz, juntamente com os registros de uso de PSTN relacionados e rotas de voz, porque quando eles clicam nesse link em seus dispositivos móveis, uma chamada de saída do Skype for Business Server será o resultado. 
