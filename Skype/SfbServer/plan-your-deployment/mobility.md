---
title: Plano de mobilidade para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planeje sua implementação do Mobility for Skype for Business Server.
ms.openlocfilehash: 6452154db1047cfe91a7c8ceaf6ee6c63b94ee6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810071"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Plano de mobilidade para o Skype for Business Server
 
Planeje sua implementação do Mobility for Skype for Business Server.
  
Com o Skype for Business Server, você pode implantar o recurso mobilidade para fornecer a funcionalidade do Skype for Business Server em dispositivos móveis. Este artigo fornece detalhes sobre o recurso Mobilidade e ajuda você a planejar sua implantação.
  
O recurso mobilidade do Skype for Business Server é capaz de suportar clientes móveis para o Skype for Business, bem como clientes do Lync voltando para 2010. Depois de implantado, os usuários podem se conectar à sua implantação do Skype for Business Server usando dispositivos móveis compatíveis com iOS, Android e Windows Phone para tirar proveito de vários recursos diferentes, incluindo recursos do Enterprise Voice. Incluímos uma lista parcial abaixo, e você também pode verificar a comparação de recursos do cliente de desktop para [o Skype for Business](clients-and-devices/desktop-feature-comparison.md) para obter mais informações:
  
- Enviar e receber mensagens
    
- Exibir presença
    
- Exibir contatos
    
- Clique para ingressar em uma conferência
    
- Telefonar via trabalho
    
- Alcance de número único
    
- Caixa postal
    
- Notificação de chamada perdida
    
- Voice over IP (VoIP)
    
- Vídeo do participante (H.264)
    
- Exibindo o conteúdo da reunião (PowerPoint e compartilhamento de área de trabalho/aplicativo)
    
Tudo isso é feito por meio da API Web de Comunicações Unificadas ou do UCWA. O UCWA foi introduzido pela primeira vez no Lync Server 2013 e ainda está em uso para o Skype for Business Server. Há uma funcionalidade adicional para se comunicar com clientes do Lync 2010, e esse é o Serviço de Mobilidade (MCX). Esses são serviços complementares, permitindo que os clientes do Lync Server 2010 e 2013, bem como clientes do Skype for Business, acessem as implantações do Skype for Business Server com êxito.
  
> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
  
É importante observar que, embora todos esses recursos sejam disponibilizados após a implementação da Mobilidade, eles podem funcionar de forma um pouco diferente em alguns dispositivos. Temos um site que discute quais recursos funcionam em quais dispositivos, na comparação de recursos do cliente [móvel para o Skype for Business.](clients-and-devices/mobile-feature-comparison.md) Também temos algumas excelentes informações de dispositivo e sistema operacional em [Planejar clientes e dispositivos.](clients-and-devices/clients-and-devices.md)
  
A mobilidade usa o recurso Descoberta Automática, que permite que os clientes localizem automaticamente os serviços Web do Skype for Business Server sem que os usuários precisem inserir URLs (eles nem precisarão se conhecer). Se você precisar solucionar problemas, ainda há suporte para a entrada manual de URLs.
  
As notificações por push também são compatíveis, para quando o aplicativo Skype for Business não estiver em execução em segundo plano (ou para dispositivos móveis que não suportam aplicativos em execução em segundo plano). Uma notificação por push é enviada a um dispositivo móvel sobre um evento que ocorre quando o dispositivo ou aplicativo está inativo. Um bom exemplo é a falta de uma mensagem de IM quando o telefone não está ativo, o que resultaria em uma notificação por push sendo enviada (isso é apresentado como uma notificação do sistema ou uma notificação, como quando o aplicativo está em execução em segundo plano). Com as notificações por push, os usuários não perderão as chamadas de voz ou de IM.
  
Para obter mais informações, temos as seguintes seções:
  
- [Componentes de mobilidade](mobility.md#MobilityComponents)
    
- [Topologias com suporte](mobility.md#SupportedTopos)
    
- [Requisitos técnicos](mobility.md#TechRequirements)
    
- [Definindo suas necessidades de mobilidade](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componentes de mobilidade
<a name="MobilityComponents"> </a>

Há quatro serviços que consistem em Mobilidade para Skype for Business Server:
  
- **Unified Communications Web API (UCWA)**
    
    Fornece serviços para comunicações em tempo real com clientes móveis e da Web para o Skype for Business Server. Quando o Skype for Business Server é implantado, um diretório virtual do UCWA é criado nos serviços Web internos e externos. Um componente virtual nesse diretório virtual que aceita chamadas de clientes habilitados para UCWA. Os aplicativos cliente se comunicam por meio de uma interface REST (transferência de estado representacional) para:
    
  - presença
    
  - contacts
    
  - mensagens instantâneas (IM)
    
  - VoIP
    
  - videoconferência
    
  - colaboração
    
    O UCWA usa um canal baseado em P-GET para enviar eventos, como uma chamada de entrada, um IM de entrada ou uma mensagem para o aplicativo cliente.
    
- **Mobility service (MCX)**
    
    Dá suporte à funcionalidade do Skype for Business Server, como IM, presença e contatos, em dispositivos móveis. O serviço mobility é instalado em cada Servidor front-end em cada pool que se destina a dar suporte à funcionalidade do Skype for Business Server em dispositivos móveis. Quando você instala o Skype for Business Server 2015, um novo diretório virtual (Mcx) é criado nos sites internos e externos em seus Servidores Front-End.
    
    > [!NOTE]
    > O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
  
- **Serviço de descoberta automática**
    
    Identifica a localização do usuário e permite que dispositivos móveis e outros clientes do Skype for Business localizem recursos (como ASLS internas e externas dos Serviços Web do Skype for Business Server, a URL Mcx ou a URL do UCWA), independentemente do local da rede. A descoberta automática usa nomes de host codificadas (lyncdiscoverinternal para usuários dentro da rede, lyncdiscover para usuários fora da rede) e o domínio SIP do usuário. Ele dá suporte a conexões de cliente que usam HTTP ou HTTPS. 
    
    O serviço Descoberta Automática é instalado em cada Servidor Front-End e em cada Diretor em cada pool destinado a dar suporte à funcionalidade do Skype for Business Server em dispositivos móveis. Quando você instala o serviço, um novo diretório virtual (Descoberta Automática) é criado sob os sites internos e externos em seus Servidores Front-End e Diretores.
    
- **Serviço de notificação por push**
    
    Um serviço baseado em nuvem localizado em seu data center do Skype for Business Online. Em telefones que não têm o cliente Skype for Business em execução em segundo plano, quando ocorre um novo evento, a notificação de um evento perdido (chamada de notificação por push) é enviada ao dispositivo móvel. O serviço mobility envia uma notificação para o mpNS (serviço de notificação por push), que a envia para o dispositivo móvel. Em seguida, o usuário pode responder à notificação em seu dispositivo móvel para ativar o aplicativo. Um Servidor de Borda é necessário para essa funcionalidade.
    
## <a name="supported-topologies"></a>Topologias suportadas
<a name="SupportedTopos"> </a>

Temos os seguintes aplicativos do Skype for Business Server com suporte para seu planejamento de topologia:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
Você deve ser capaz de usar essa funcionalidade com servidores de borda do Skype for Business Server ou servidores de borda do Lync Server 2013.
  
O serviço de Mobilidade é suportado em Servidores Front-End quando alocado com a função de Servidor de Mediação, com duas interfaces de rede, mas você precisa tomar as medidas apropriadas para configurar essas interfaces. Você precisará atribuir endereços IP à interface específica que se comunicará como o Servidor de Mediação e à interface IP de rede que se comunicará como o Servidor Front-End. Você pode fazer isso no Construtor de Topologia selecionando o endereço IP correto para cada serviço, em vez de usar a seleção padrão Usar todos os endereços **IP configurados.**
  
## <a name="technical-requirements"></a>Requisitos técnicos
<a name="TechRequirements"> </a>

É importante planejar os vários cenários de aplicativos móveis que seus usuários móveis podem encontrar. Por exemplo, alguém pode começar a usar um aplicativo móvel fora do trabalho conectando-se por meio de uma rede 3G e, em seguida, alternar para a rede Wi-Fi corporativa quando chegar ao trabalho. Eles podem mudar para 4G ao sair do edifício. O planejamento agora permitirá que você suporte essas transições de rede e garanta uma experiência de usuário consistente.
  
### <a name="dns-configuration"></a>Configuração de DNS

Os serviços de Mobilidade Mcx e UCWA usam DNS da mesma maneira. Com a Descoberta Automática, os dispositivos móveis usam o DNS para localizar recursos. Durante a análise de DNS, uma conexão é tentada com o FQDN associado ao registro DNS interno (lyncdiscoverinternal.[ nome de domínio interno]). Se o registro DNS interno não puder ser usado para fazer essa conexão, será tentada uma segunda conexão, desta vez com o registro DNS externo (lyncdiscover.[ sipdomain]). Então, por que ter dois? Um dispositivo móvel que seja interno à sua rede poderá usar a URL interna de Descoberta Automática. Dispositivos móveis externos usarão a URL externa de Descoberta Automática. Em ambos os casos, o serviço descoberta automática retornará todas as URLs de serviço Web para o pool de hospedagem do usuário, que inclui o serviço de Mobilidade (Mcx e UCWA).
  
Espera-se que as solicitações de Descoberta Automática externas passarão pelo proxy reverso que você configurou para o Skype for Business Server. No entanto, tanto a URL interna do Serviço de Mobilidade quanto a URL externa do Serviço de Mobilidade estão associadas ao FQDN dos Serviços Web externos. Portanto, independentemente de um dispositivo móvel ser interno ou externo à sua rede, o dispositivo sempre se conecta ao serviço de Mobilidade do Skype for Business Server externamente, por meio de seu proxy reverso.
  
> [!NOTE]
> Como vimos, todo o tráfego do serviço de Mobilidade (interno e externo) passará pelo proxy reverso. Mas, às vezes, surge um problema quando o tráfego interno sai de uma interface, apenas para tentar e voltar na mesma interface. Isso pode violar as regras de segurança de spoofing (formalmente chamada de spoofing de pacotes TCP). Você precisará permitir que o **Hair Pinning** tenha a função Mobilidade.
  
> [!NOTE]
> Se você estiver pronto para fazer isso, também pode optar por usar um proxy reverso separado do firewall (para fins de segurança, a prevenção contra spoofing sempre deve ser imposta em seu firewall). Dessa forma, o hairpin pode acontecer na interface externa do seu proxy reverso, em vez da interface externa do firewall. Isso permite que você detecte a spoofing corretamente no firewall enquanto você adote a regra em seu proxy reverso e receba sua funcionalidade de mobilidade. 
  
> [!NOTE]
> Se você seguir essa rota, use o host DNS ou os registros CNAME para definir o proxy reverso para o comportamento de hairpin (não o firewall), se possível. 
  
Há algumas coisas que você precisará configurar para dar suporte a usuários dentro e fora da rede corporativa.
  
Estas são as regras para FQDNs da Web internos e externos:
  
- Novos registros DNS CNAME ou A (host, se IPv6, AAAA), para descoberta automática.
    
- Nova regra de firewall, se você quiser dar suporte a notificações por push através de sua Wi-Fi rede.
    
- Nomes alternativos de assunto em certificados de servidor interno e certificados de proxy reverso, para descoberta automática.
    
- A configuração balanceada de carga de hardware do Servidor Front End altera a afinidade da origem.
    
Estes são os requisitos de topologia necessários para dar suporte ao Serviço de Mobilidade e ao Serviço de Descoberta Automática:
  
- O FQDN da Web interno do pool de Front End deve ser diferente do FQDN da Web externo do pool de Front-End.
    
- O FQDN da Web interno só deve resolver e ser acessível de dentro da rede corporativa.
    
- O FQDN da Web externo só deve ser resolvido para a Internet e ser acessível por ela.
    
- Para um usuário dentro da rede corporativa, a URL do serviço mobility deve ser endereçada ao FQDN externo da Web. Esse requisito é para o serviço de Mobilidade e se aplica somente a essa URL.
    
- Para um usuário fora da rede corporativa, a solicitação deve ir para o FQDN da Web externo do pool de Front-End ou Diretor.
    
Se você suportar a descoberta automática, precisará fazer os seguintes registros DNS para cada domínio SIP:
  
- Um registro DNS interno para dar suporte a usuários móveis que se conectam de dentro da rede da sua organização.
    
- Um registro DNS externo ou público para dar suporte a usuários móveis que se conectam pela Internet.
    
A URL de descoberta automática interna não deve ser acessível de fora da rede interna. A URL de descoberta automática externa não deve ser abordada de dentro da sua rede. Mas se isso não for possível para a URL externa, sua funcionalidade de cliente móvel provavelmente não será afetada, porque a URL interna sempre será tentada primeiro.
  
### <a name="port-and-firewall-requirements"></a>Requisitos de porta e firewall

Abordamos grande parte disso em nossa outra documentação, mas especificamente para Mobilidade, você vai querer ter as seguintes portas abertas em sua rede corporativa do Wi-Fi se tiver usuários em um Aparelho de Filial Sustentável (SBA):
  
- UcwaSipExternalListeningPort requer 5088.
    
- UcwaSipPrimaryListeningPort requer 5089.
    
### <a name="certificate-requirements"></a>Requisitos de Certificação

Se você estiver usando a descoberta automática para seus clientes móveis do Skype for Business, precisará modificar as listas SAN (nome alternativo da assunto) em seus certificados para dar suporte a conexões seguras de seus clientes móveis. Se você já tiver certificados no local, precisará solicitar e atribuir novos certificados com as entradas SAN descritas aqui. Isso precisará ser feito para cada Servidor front-end e Diretor (se em seu ambiente) que executa o serviço de Descoberta Automática. Também recomendamos modificar as listas san em seus certificados de proxy reverso, adicionando entradas SAN para cada domínio SIP em sua organização.
  
Esse deve ser um processo simples se você estiver solicitando os novos certificados de uma autoridade de certificação interna (autoridade de certificação), mas os certificados públicos são mais complexos e potencialmente muito mais caros para solicitar outra vez, sem mencionar que pode ser caro adicionar muitos domínios SIP a um novo certificado público. Nessa situação, há uma abordagem com suporte, mas **não recomendada.** Você pode configurar seu proxy reverso para fazer a solicitação inicial do serviço descoberta automática pela porta 80, que usará HTTP, em vez da porta 443, que é HTTPS (e 443 é a configuração padrão). Essa solicitação de entrada será redirecionada para a porta 8080 em seu pool de Front-End ou Diretor. Ao fazer isso, você não precisará fazer alterações de certificado, porque esse tráfego não está usando HTTPS para solicitações. Mas, novamente, não recomendamos isso, embora funcione para você.
  
### <a name="windows-and-iis-requirements"></a>Requisitos do Windows e do IIS

Você deve ter uma versão do Windows Server com suporte para seu ambiente do Skype for Business Server. Como resultado, você também deve ter o IIS 8 ou o IIS 8.5 para suas necessidades de mobilidade. Será necessário fazer algumas alterações nas configurações de ASP.NET padrão, mas o instalador do serviço mobility fará isso automaticamente.
  
### <a name="hlb-requirements"></a>Requisitos de HLB

Se você estiver usando uma topologia para o Skype for Business Server que inclua um HLB para seu pool de Front-End (que seria qualquer topologia que inclua mais de um Servidor Front-End), os VIPs (IPs virtuais) dos Serviços Web externos para tráfego de Serviços Web precisarão ser configurados para origem. A afinidade de origem ajuda a garantir que várias conexões de um único cliente sejam enviadas ao mesmo servidor para manter o estado da sessão.
  
Se você planeja dar suporte a clientes móveis do Skype for Business somente pela rede Wi-Fi interna, configure seus VIPs de Serviços Web internos para origem, conforme descrito para VIPs de Serviços Web externos. Nessa situação, você deve usar source_addr (ou TCP) para os VIPs de Serviços Web internos no HLB.
  
Para obter detalhes sobre tudo isso, consulte os [requisitos de balanceamento de carga para a documentação do Skype for Business.](network-requirements/load-balancing.md)
  
### <a name="reverse-proxy-requirements"></a>Requisitos de proxy reverso

Para dar suporte à descoberta automática para clientes móveis do Skype for Business, você precisará atualizar a regra de publicação atual da seguinte forma:
  
- Se você decidir atualizar as listas de SAN em seus certificados de proxy reverso e estiver usando HTTPS para a solicitação de serviço de Descoberta Automática inicial, será necessário atualizar a regra de publicação na Web para lyncdiscover. \<sipdomain\> Isso é geralmente combinado com o rul de publicação para a URL dos Serviços Web externos no pool de Front-End.
    
- Se você decidiu usar HTTP para a solicitação inicial do serviço descoberta automática para evitar a necessidade de atualizar a lista san para seus certificados de proxy reverso (o que não recomendamos), você precisará criar uma nova regra de publicação na Web para a porta HTTP/TCP 80, se ainda não houver uma. Se essa regra existir, atualize-a para incluir um lyncdiscover.\<sipdomain\> entrada.
    
## <a name="defining-your-mobility-needs"></a>Definindo suas necessidades de mobilidade
<a name="MobilityNeeds"> </a>

Agora que analisamos as topologias, componentes e requisitos técnicos, vamos analisar o que sua organização pode precisar em termos de implementação de Mobilidade.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Você deseja usar a descoberta automática para clientes móveis do Skype for Business?

Recomendamos que você use a descoberta automática. Ele exigirá a criação de novos registros DNS internos e externos, conforme documentado na seção Requisitos Técnicos acima. Com a descoberta automática, os clientes do Skype for Business podem localizar automaticamente os Serviços Web do Skype for Business Server de qualquer local, sem a necessidade de uma URL para ser inserida manualmente.
  
Você pode usar configurações manuais se precisar. Essas URLs precisarão ser inseridas pelos usuários em seus dispositivos móveis:
  
- **https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** para acesso externo.
    
- **https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** para acesso interno.
    
Novamente, recomendamos o uso da descoberta automática. Você pode achar as configurações manuais úteis para a solução de problemas.
  
### <a name="are-you-going-to-support-push-notifications"></a>Você vai dar suporte a notificações por push?

As notificações por push são usadas para aplicativos móveis que suportam essa funcionalidade para notificar um usuário de eventos enquanto o aplicativo não está ativo. Seu Servidor de Borda precisará ter um relacionamento de federação com seu Serviço de Notificação por Push do Skype for Business Server baseado em nuvem, que é encontrado no datacenter do Skype for Business Online. Você precisará executar um cmdlet para habilitar notificações por push.
  
> [!NOTE]
> Se você ainda tiver alguém usando clientes do Lync Server 2010, eles precisarão da porta TCP 5223 de saída aberta em sua rede WiFi corporativa. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Você deseja que todos os seus usuários acessem todos os recursos de Mobilidade ou deseja especificar os usuários que podem acessar esses recursos?

Temos uma tabela para ajudar com alguns dos recursos que estão disponíveis para todos os usuários e se eles estão definidos dessa forma ou não por padrão. Para uma lista completa, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Os escopos de todos esses recursos são Global/Site/Usuário. 
  
|**Característica**|**Nome do Parâmetro**|**Descrição**|**Configuração Padrão**|
|:-----|:-----|:-----|:-----|
|Habilitar Mobilidade  <br/> |EnableMobility  <br/> |Controla os usuários em um determinado escopo que têm o cliente móvel do Skype for Business instalado. Se a política for definida como False, os usuários não poderão entrar com o cliente.  <br/> |Verdadeiro  <br/> |
|Outside Voice  <br/> |EnableOutsideVoice  <br/> |Permite que um usuário use a Chamada Via Trabalho, que permite que os usuários enviem e recebam chamadas usando seu número de trabalho em vez de seu número de celular. Se estiver definido como False, os usuários não poderão fazer ou receber chamadas no celular ao usar o número de telefone do trabalho.  <br/> |Verdadeiro  <br/> |
|Habilitar áudio e vídeo IP  <br/> |EnableIPAudioVideo  <br/> |De acordo com o padrão, ele permite que um usuário use VoIP para fazer ou receber chamadas telefônicas ou de vídeo em seu dispositivo móvel. Quando seu valor for definido com False, os usuários não poderão usar o dispositivo móvel para fazer uma dessas coisas.  <br/> |Verdadeiro  <br/> |
|Exigir WiFi para áudio IP  <br/> |RequireWiFiForIPAudio  <br/> |Define se um cliente precisará fazer e receber chamadas via VoIP em WiFi em vez de uma rede de dados da rede celular. Se estiver definido como True, os usuários só poderão fazer e receber chamadas VoIP quando eles estão conectados via WiFi.  <br/> |Falso  <br/> |
|Exigir WiFi para Vídeo IP  <br/> |RequireWiFiForIPVideo  <br/> |Define se um cliente precisará fazer e receber chamadas de vídeo em WiFi em vez de uma rede de dados da rede celular. Se estiver definido como True, os usuários só poderão fazer e receber chamadas VoIP quando eles estão conectados via WiFi.  <br/> |Falso  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Os usuários que não estão habilitados para o Enterprise Voice devem ser capazes de usar Clique para Ingressar para ingressar em conferências?

Para que os usuários tenham acesso aos recursos de Mobilidade e Telefonar via Trabalho, eles precisam estar habilitados para o Enterprise Voice. Porém, mesmo que não sejam habilitados, eles ainda poderão ingressar em conferências clicando em um link em seu dispositivo móvel, mas somente se eles têm uma política de voz apropriada atribuída a eles. Você pode:
  
- atribuir uma política de voz específica a esses usuários ou
    
- certifique-se de que existe uma política global ou de nível de site e se aplica a elas.
    
De qualquer forma, a política de voz que você atribuir precisa ter registros de uso da PSTN (Rede Telefônica Pública Comutado) e rotas que definirão onde os usuários poderão discar para participar de conferências.
  
> [!NOTE]
> Os usuários móveis que quiserem usar Clique para Ingressar exigem uma política de voz, juntamente com os registros de uso de PSTN relacionados e rotas de voz, pois quando clicarem nesse link em seus dispositivos móveis, uma chamada de saída do Skype for Business Server será o resultado. 
  

