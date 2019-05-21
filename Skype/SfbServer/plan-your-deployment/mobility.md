---
title: Plano de mobilidade para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planeje sua implementação de mobilidade para o Skype for Business Server.
ms.openlocfilehash: 8b0ba8dd4ae07d3330a8ca722a1101c6b41a7cec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297320"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Plano de mobilidade para o Skype for Business Server
 
Planeje sua implementação de mobilidade para o Skype for Business Server.
  
Com o Skype for Business Server, você pode implantar o recurso de mobilidade para fornecer a funcionalidade do Skype for Business Server em dispositivos móveis. Este artigo fornece detalhes sobre o recurso de mobilidade e ajuda você a planejar sua implantação.
  
O recurso de mobilidade para o Skype for Business Server é capaz de dar suporte a clientes móveis para o Skype for Business, bem como os clientes do Lync de volta para o 2010. Depois que ele for implantado, os usuários poderão se conectar à implantação do Skype for Business Server usando dispositivos móveis iOS, Android e Windows Phone compatíveis para tirar proveito de vários recursos diferentes, incluindo os recursos Enterprise Voice. Incluímos uma lista parcial abaixo, e você também pode verificar a [comparação de recursos do cliente de área de trabalho do Skype for Business](clients-and-devices/desktop-feature-comparison.md) para obter mais informações:
  
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
    
Tudo isso é feito por meio da API Web de Comunicações Unificadas (UCWA). O UCWA foi introduzido pela primeira vez no Lync Server 2013, e ainda está em uso para o Skype for Business Server. Há uma funcionalidade adicional para comunicação com clientes do Lync 2010, e esse é o serviço de mobilidade (MCX). Esses são serviços complementares, que permitem que os clientes do Lync Server 2010 e do 2013, bem como os clientes do Skype for Business, acessem as implantações do Skype for Business Server com êxito.
  
> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
É importante observar que, enquanto todos esses recursos estão disponíveis após a implementação da mobilidade, eles podem funcionar de maneira um pouco diferente em alguns dispositivos. Temos um site que discute quais recursos funcionam em quais dispositivos, em [comparação de recursos do cliente móvel para o Skype for Business](clients-and-devices/mobile-feature-comparison.md). Também temos excelentes informações sobre dispositivos e sistemas operacionais no [plano para clientes e dispositivos](clients-and-devices/clients-and-devices.md).
  
A mobilidade faz uso do recurso descoberta automática, que permite aos clientes localizar automaticamente os serviços Web do Skype for Business Server sem usuários que precisam digitar em qualquer URL (eles não precisam sequer conhecê-los). Caso você precise solucionar problemas, ainda há suporte para a entrada manual de URLs.
  
Também há suporte para notificações por push, para quando o aplicativo Skype for Business não está em execução em segundo plano (ou para dispositivos móveis que não dão suporte a aplicativos executados em segundo plano). Uma notificação por push é enviada a um dispositivo móvel sobre um evento que ocorre quando o dispositivo ou o aplicativo está inativo. Um bom exemplo é uma mensagem de mensagem instantânea ausente quando o seu telefone não está ativo, o que resultaria em uma notificação por push sendo enviada (isso é apresentado como uma notificação do sistema ou notificação, como quando o aplicativo está sendo executado em segundo plano). Com as notificações por push, os usuários não perdem mensagens instantâneas nem chamadas de voz.
  
Para obter mais informações, confira as seguintes seções:
  
- [Componentes de mobilidade](mobility.md#MobilityComponents)
    
- [Topologias com suporte](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Como definir seus requisitos de mobilidade](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de mobilidade
<a name="MobilityComponents"> </a>

Há quatro serviços que compõem o Mobility para o Skype for Business Server:
  
- **API Web de Comunicações Unificadas (UCWA)**
    
    Fornece serviços para comunicações em tempo real com clientes móveis e Web para o Skype for Business Server. Quando o Skype for Business Server é implantado, um diretório virtual do UCWA é criado nos serviços Web internos e externos. Um componente virtual nesse diretório virtual aceita chamadas de clientes habilitados para UCWA. Os aplicativos cliente se comunicam por meio de uma interface REST (transferência de estado representacional) para:
    
  - presença
    
  - contatos
    
  - IM (sistema de mensagens instantâneas)
    
  - VoIP
    
  - videoconferências
    
  - colaboração
    
    O UCWA utiliza um canal baseado em P-GET para enviar eventos, como uma chamada de entrada, uma mensagem instantânea de entrada ou uma mensagem para o aplicativo cliente.
    
- **Serviço de Mobilidade (MCX)**
    
    Compatível com a funcionalidade do Skype for Business Server, como mensagens instantâneas, presença e contatos, em dispositivos móveis. O serviço de mobilidade está instalado em cada servidor front-end em cada pool destinado a suportar a funcionalidade do Skype for Business Server em dispositivos móveis. Ao instalar o Skype for Business Server 2015, um novo diretório virtual (MCX) é criado nos sites internos e externos em seus servidores front-ends.
    
    > [!NOTE]
    > O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
- **Serviço de Descoberta Automática**
    
    Identifica o local do usuário e permite que dispositivos móveis e outros clientes do Skype for Business localizem recursos (como URLS internas e externas para os serviços Web do Skype for Business Server, a URL do MCX ou a URL do UCWA), independentemente da localização da rede. A descoberta automática usa nomes de host codificados (lyncdiscoverinternal para usuários da rede e lyncdiscover para usuários fora da rede) e o domínio SIP do usuário. Ela dá suporte a conexões de clientes que usam HTTP ou HTTPS. 
    
    O serviço de descoberta automática está instalado em todos os servidores front-end e em cada director em cada pool destinado a suportar a funcionalidade do Skype for Business Server em dispositivos móveis. Quando você instala o serviço, um novo diretório virtual (descoberta automática) é criado em sites internos e externos em seus servidores e directors front-end.
    
- **Serviço de notificação por push**
    
    Um serviço baseado na nuvem localizado no seu data center do Skype for Business online. Em telefones que não têm o cliente Skype for Business em execução em segundo plano, quando um novo evento ocorre, a notificação de um evento perdido (chamada de notificação por push) é enviada para o dispositivo móvel em vez disso. O serviço de mobilidade envia uma notificação para o serviço de notificação por push (MPNS), que o envia para o dispositivo móvel. O usuário pode então responder à notificação em seu dispositivo móvel para ativar o aplicativo. É necessário um servidor de borda para esta funcionalidade.
    
## <a name="supported-topologies"></a>Topologias suportadas
<a name="SupportedTopos"> </a>

Temos os seguintes aplicativos compatíveis com o Skype for Business Server para o planejamento de topologia:
  
- Standard Mobility Edition
    
- Mobility Enterprise Edition
    
Você deve ser capaz de usar essa funcionalidade com os servidores de borda do Skype for Business Server ou servidores de borda do Lync Server 2013.
  
O serviço de mobilidade tem suporte em servidores front-end quando posicionado com a função de servidor de mediação, com duas interfaces de rede, mas você precisa tomar as medidas necessárias para configurar essas interfaces. Você precisará atribuir endereços IP para a interface específica que se comunicará como servidor de mediação e a interface IP de rede que se comunicará como servidor front-end. Você pode fazer isso no construtor de topologias selecionando o endereço IP correto para cada serviço, em vez de usar a seleção padrão **usar todos os endereços IP** configurados.
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

É importante planejar os vários cenários de aplicativos móveis que os usuários móveis podem encontrar. Por exemplo, alguém pode começar a usar um aplicativo móvel fora do trabalho conectando-se por meio de uma rede 3G e depois mudar para a rede Wi-Fi corporativa ao chegar ao trabalho. Elas podem mudar para 4G ao deixar seu prédio. Planeje agora para poder dar suporte a essas transições de rede e garantir uma experiência do usuário consistente.
  
### <a name="dns-configuration"></a>Configuração de DNS

Os serviços de mobilidade MCX e UCWA usam o DNS da mesma maneira. Com a Descoberta Automática, os dispositivos móveis usam DNS para localizar recursos. Durante a pesquisa de DNS, é feita uma tentativa de conexão com o FQDN que está associado ao registro DNS interno (lyncdiscoverinternal.[nome de domínio interno]). Se o registro DNS interno não puder ser usado para estabelecer essa conexão, será feita uma segunda tentativa de conexão, dessa vez com o registro DNS externo (lyncdiscover.[sipdomain]). Então, por que há dois? Um dispositivo móvel que é interno à sua rede poderá usar a URL de Descoberta Automática interna. Dispositivos móveis externos usarão a URL de Descoberta Automática externa. Em ambos os casos, o serviço descoberta automática retornará todas as URLs do serviço Web para o pool inicial do usuário, que inclui o serviço de mobilidade (MCX e UCWA).
  
Espera-se que as solicitações de descoberta automática externa sejam feitas pelo proxy reverso que você configurou para o Skype for Business Server. No entanto, tanto a URL do serviço de mobilidade interna quanto a URL do serviço de mobilidade externa são associadas ao FQDN de serviços Web externos. Portanto, independentemente de um dispositivo móvel ser interno ou externo à sua rede, o dispositivo sempre se conecta ao serviço de mobilidade do Skype for Business Server externamente, por meio do seu proxy reverso.
  
> [!NOTE]
> Como acabamos de observar, todo o tráfego do serviço de mobilidade (interno e externo) passará pelo proxy reverso. Porém, às vezes, surge um problema quando o tráfego interno sai por uma interface, para depois tentar voltar pela mesma interface. Isso pode violar suas regras de segurança contra falsificação (formalmente, isso é chamado de falsificação de pacote TCP). Você precisará permitir que a **fixação de cabelo** seja a função de mobilidade.
  
> [!NOTE]
> Se estiver pronto para fazer isso, você também pode optar por usar um proxy inverso que seja separado do seu firewall (para fins de segurança, a prevenção de spoof deve ser sempre imposta em seu firewall). Dessa forma, o conecte pode acontecer na interface externa do seu proxy reverso, em vez da interface externa do seu firewall. Isso permite que você detecte a falsificação apropriadamente no seu firewall enquanto libera a regra em seu proxy reverso e obtém a funcionalidade de mobilidade. 
  
> [!NOTE]
> Se você usar essa rota, use o host DNS ou os registros CNAME para definir o proxy inverso para o comportamento conecte (não o firewall), se possível. 
  
Há alguns itens que você precisa configurar para dar suporte aos usuários dentro e fora da rede corporativa.
  
Estas são as regras para FQDNs Web internos e externos:
  
- Novos registros DNS CNAME ou A (host, se IPv6, AAAA), para descoberta automática.
    
- Nova regra de firewall, se você quiser dar suporte a notificações de envio pela sua rede Wi-Fi.
    
- Nomes alternativos de assunto em certificados de servidor internos e certificados de proxy reverso para descoberta automática.
    
- Configuração balanceada de carga de hardware do servidor front-end altera a afinidade de origem.
    
Estes são os requisitos de topologia necessários para dar suporte ao serviço de mobilidade e ao serviço de descoberta automática:
  
- O FQDN da Web interna do pool de front-end deve ser diferente do FQDN da Web externa do pool de front-end.
    
- O FQDN interno da Web só deve ser resolvido para a rede corporativa e ser acessível nela.
    
- O FQDN interno da Web só deve ser resolvido para a Internet e ser acessível nela.
    
- Para um usuário dentro da rede corporativa, a URL do serviço de mobilidade deve ser endereçada ao FQDN da Web externa. Esse requisito é para o serviço de mobilidade e aplica-se somente a essa URL.
    
- Para um usuário fora da rede corporativa, a solicitação deve acessar o FQDN da Web externo do pool ou do diretor de front-end.
    
Se você dá suporte à descoberta automática, precisa criar os seguintes registros DNS para cada domínio SIP:
  
- Um registro DNS interno para dar suporte a usuários móveis que se conectam da rede de sua organização
    
- Um registro DNS externo ou público para dar suporte a usuários móveis que se conectam pela Internet.
    
A URL de descoberta automática interna não deve ser endereçável de fora da rede interna. A URL de descoberta automática externa não deve ser endereçável de dentro da rede. Porém, se isso não for possível para a URL externa, sua funcionalidade de cliente móvel provavelmente não será afetada, pois a URL interna será sempre tentada primeiro.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de Firewall e de Porta

Abordamos a maioria disso em nossa outra documentação, mas especificamente para a mobilidade, você desejará ter as seguintes portas abertas na sua rede Wi-Fi corporativa se tiver usuários hospedados em um aparelho de ramificação sobreviventes (SBA):
  
- UcwaSipExternalListeningPort requer 5088.
    
- UcwaSipPrimaryListeningPort requer 5089.
    
### <a name="certificate-requirements"></a>Requisitos de certificado

Se você estiver usando a descoberta automática para seus clientes móveis do Skype for Business, precisará modificar as listas SAN (nome alternativo do requerente) em seus certificados para dar suporte a conexões seguras de seus clientes móveis. Se já tiver certificados, você precisará solicitar e atribuir novos certificados com as entradas SAN descritas aqui. Isso precisará ser feito para cada servidor e diretor de front-end (se estiver em seu ambiente) que executa o serviço de descoberta automática. Também recomendamos modificar as listas SAN em seus certificados de proxy reverso, adicionar entradas de SAN a cada domínio SIP em sua organização.
  
Isso deve ser um processo simples se você estiver solicitando a desativação de uma CA interna (autoridade de certificação), mas os certificados públicos são mais complexos e podem ser muito mais caros de resolicitar, e não mencionar que é dispendioso adicionar muitos SIP domínios para um novo certificado público. Nessa situação, há uma abordagem com suporte, mas **não recomendado**. Você pode configurar seu proxy reverso para fazer a solicitação de serviço inicial de descoberta automática pela porta 80, que usará HTTP, em vez de porta 443, que é HTTPS (e 443 é a configuração padrão). Essa solicitação de entrada será redirecionada para a porta 8080 em seu pool ou diretor de front-end. Fazendo isso, você não precisará fazer alterações nos certificados, pois esse tráfego não usa HTTPS para solicitações. Porém, novamente, não recomendamos isso, embora funcione para você.
  
### <a name="windows-and-iis-requirements"></a>Requisitos do Windows e do IIS

Você deve ter uma versão do Windows Server com suporte para o seu ambiente do Skype for Business Server. Como resultado, também deve ter o IIS 8 ou o IIS 8.5 para suas necessidades de mobilidade. Será necessário haver algumas alterações nas configurações padrão do ASP.NET, mas o instalador do serviço de mobilidade fará isso automaticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Se você estiver usando uma topologia para o Skype for Business Server que inclui um HLB para o seu pool Front-end (que seria qualquer topologia que inclua mais de um servidor front-end), os IPs virtuais (VIPs) de serviços Web externos para o tráfego de serviços Web precisarão ser configurados para a fonte. A afinidade da origem garante que várias conexões de um único cliente sejam enviadas ao mesmo servidor para manter o estado da sessão.
  
Se você planeja dar suporte a clientes móveis do Skype for Business apenas em sua rede Wi-Fi interna, configure seus VIPs internos de serviços Web para a origem, conforme descrito para VIPs de serviços Web externos. Nessa situação, você deve usar a afinidade source_addr (ou TCP) para os VIPs de serviços Web internos no HLB.
  
Para obter mais detalhes, confira a documentação [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md).
  
### <a name="reverse-proxy-requirements"></a>Requisitos de proxy reverso

Para dar suporte à descoberta automática para clientes móveis do Skype for Business, você precisará atualizar a regra de publicação atual da seguinte maneira:
  
- Se você decidir atualizar as listas de SAN em seus certificados de proxy reverso e estiver usando HTTPS para a solicitação de serviço de descoberta automática inicial, será necessário atualizar a regra de publicação da Web para lyncdiscover. \<sipdomain\>. Isso geralmente é combinado com o RUL de publicação para a URL de serviços Web externos no pool de front-ends.
    
- Se você decidiu usar HTTP para a solicitação inicial de serviço de descoberta automática para evitar ter que atualizar a lista SAN para seus certificados de proxy reverso (que não recomendamos), será necessário criar uma nova regra de publicação na Web para a porta HTTP/TCP 80, se não houver uma foi. Se essa regra existir, atualize-a para incluir um lyncdiscover. \<entrada\> sipdomain.
    
## <a name="defining-your-mobility-needs"></a>Como definir seus requisitos de mobilidade
<a name="MobilityNeeds"> </a>

Agora que analisamos as topologias, componentes e requisitos técnicos, vamos ver o que a sua organização pode precisar em termos de uma implementação de mobilidade.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Você deseja usar a descoberta automática para clientes móveis do Skype for Business?

É altamente recomendável que você use a descoberta automática. Ela exigirá a criação de novos registros DNS internos e externos, conforme documentado na seção Requisitos técnicos acima. Com o recurso de descoberta automática, os clientes do Skype for Business podem localizar automaticamente os serviços Web do Skype for Business Server de qualquer local, sem precisar que uma URL seja inserida manualmente.
  
Você poderá usar as configurações manuais, se precisar. Estas URLs precisarão ser inseridas pelos usuários em seus dispositivos móveis:
  
- **https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root** para acesso externo.
    
- **https://\<IntPoolFQDN\>/autodiscover/autodiscoverservice.svc/root** para acesso interno.
    
Mais uma vez, recomendamos o uso da descoberta automática. As configurações manuais podem ser úteis para solucionar problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>Você dará suporte a notificações por push?

As notificações por push são usadas para aplicativos móveis compatíveis com essa funcionalidade para notificar usuários da ocorrência de eventos enquanto o aplicativo não está ativo. Seu servidor de borda precisará ter uma relação de Federação com o serviço de notificação por push do Skype for Business Server baseado em nuvem, que está disponível no datacenter do Skype for Business online. Você precisará executar um cmdlet para habilitar notificações por push.
  
> [!NOTE]
> Se você ainda tiver alguém que esteja usando o Lync Server 2010, será necessário ter a porta TCP 5223 aberta no seu ambiente de rede WiFi. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Você quer que todos os usuários acessem todos os recursos de mobilidade ou deseja especificar os usuários que podem acessar esses recursos em vez disso?

Temos uma tabela para ajudar com alguns dos recursos que estão disponíveis para todos os usuários e se estão definidos dessa forma ou não por padrão. Para ver uma lista completa, confira [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Os escopos para todos esses recursos são Global/Site/Usuário. 
  
|**Recurso**|**Nome do parâmetro**|**Descrição**|**Configuração padrão**|
|:-----|:-----|:-----|:-----|
|Habilitar mobilidade  <br/> |EnableMobility  <br/> |Controla os usuários em um determinado escopo que têm o cliente Skype for Business Mobile instalado. Se a política for definida como False, os usuários não poderão entrar no serviço com o cliente.  <br/> |True  <br/> |
|Voz Externa  <br/> |EnableOutsideVoice  <br/> |Habilita o usuário a utilizar Telefonar via Trabalho. Esse recurso permite enviar e receber chamadas usando o número comercial em vez do número do celular. Se essa configuração for definida como False, os usuários não poderão fazer nem receber chamadas no celular ao usar o número de telefone comercial.  <br/> |True  <br/> |
|Habilitar áudio e vídeo por IP  <br/> |EnableIPAudioVideo  <br/> |Quando definida como padrão, essa configuração permite que um usuário utilize VoIP para fazer ou receber chamadas telefônicas ou chamadas de vídeo em seu dispositivo móvel. Quando essa configuração é definida como False, os usuários não podem usar seus dispositivos móveis para realizar essas ações.  <br/> |True  <br/> |
|Requer WiFi para áudio por IP  <br/> |RequireWiFiForIPAudio  <br/> |Define se um cliente precisará fazer e receber chamadas por VoIP sobre Wi-Fi, em vez de uma rede de dados celular. Se essa configuração for definida como True, os usuários só poderão fazer e receber chamadas por VoIP quando estiverem conectados via Wi-Fi.  <br/> |False  <br/> |
|Requer WiFi para vídeo por IP  <br/> |RequireWiFiForIPVideo  <br/> |Define se um cliente precisará fazer e receber chamadas de vídeo por Wi-Fi, em vez de uma rede de dados celular. Se essa configuração for definida como True, os usuários só poderão fazer e receber chamadas por VoIP quando estiverem conectados via Wi-Fi.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Os usuários que não estão habilitados para Enterprise Voice podem usar Clique para Ingressar para ingressar em conferências?

Para que os usuários tenham acesso aos recursos da mobilidade e liguem pelo trabalho, eles precisam estar habilitados para o Enterprise Voice. Porém, mesmo se não estiverem habilitados, eles ainda poderão participar de conferências clicando em um link em seu dispositivo móvel, mas apenas se tiverem uma política de voz apropriada atribuída a eles. Você pode:
  
- atribuir uma política de voz específica a esses usuários ou
    
- garantir que exista uma política global ou uma política de nível de site e que ela se aplique a eles.
    
De qualquer forma, a política de voz que você atribuir precisará ter registros de uso de PSTN (rede telefônica pública comutada) e rotas que definirão para onde os usuários poderão discar para ingressar em conferências.
  
> [!NOTE]
> Os usuários móveis que desejam usar o clique para ingressar exigem uma política de voz, juntamente com os registros de uso de PSTN relacionados e rotas de voz, porque quando eles clicam nesse link em seus dispositivos móveis, uma chamada de saída do Skype for Business Server será o resultado. 
  

