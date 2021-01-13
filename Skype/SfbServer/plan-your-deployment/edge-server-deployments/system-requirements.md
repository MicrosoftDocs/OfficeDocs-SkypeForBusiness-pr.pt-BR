---
title: Requisitos de sistema do Servidor de Borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Resumo: saiba mais sobre os requisitos do sistema para o Servidor de Borda no Skype for Business Server.'
ms.openlocfilehash: e066249498febbd5e622546533f49422320c7c87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813761"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos de sistema do Servidor de Borda no Skype for Business Server
 
**Resumo:** Saiba mais sobre os requisitos de sistema para o Servidor de Borda no Skype for Business Server.
  
Quando se trata de sua implantação do Skype for Business Server Edge Server, estas são as coisas que você precisará fazer para o servidor ou servidores que estão no próprio ambiente, bem como planejar a estrutura do ambiente. Para obter mais informações sobre topologia, DNS, certificados e outras preocupações de infraestrutura, consulte a documentação de requisitos ambientais.
  
## <a name="components"></a>Componentes

Ao discutir o ambiente do Servidor de Borda, estamos fazendo referência a componentes que são, na maioria das vezes, implantados em uma rede de perímetro (ou seja, em um grupo de trabalho ou em um domínio que está fora de sua estrutura de domínios do Skype for Business Server).
  
Tendo isso em mente, estes são os componentes que você precisará ter em mente para implantar sua Borda com êxito:
  
- [Servidores de Borda](system-requirements.md#EdgeServers)
    
- [Proxies reversos](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Diretores](system-requirements.md#Directors) (eles são opcionais e, se eles estão incluídos, eles estarão localizados em sua rede interna)
    
- [Balanceadores de](system-requirements.md#LoadBalancers) carga (você pode ter balanceamento de carga DNS ou um HLB (balanceador de carga de hardware), mas para um único Servidor de Borda, isso não é necessário)
    
Temos mais detalhes sobre cada um deles abaixo:
  
### <a name="edge-servers"></a>Servidores de Borda
<a name="EdgeServers"> </a>

Estes são os servidores do Skype for Business implantados em seu ambiente de perímetro. Sua função é enviar e receber tráfego de rede para usuários externos para os serviços oferecidos pela sua implantação interna do Skype for Business Server. Para fazer isso com êxito, cada Servidor de Borda executa:
  
- **Serviço de Borda de** Acesso: fornece um ponto de conexão único e confiável para o tráfego SIP (Session Initiation Protocol) de saída e de entrada.
    
- **Serviço de Borda de** Webconferência: permite que usuários externos participem de reuniões hospedadas em seu ambiente interno do Skype for Business Server.
    
- **Serviço de Borda A/V:** disponibiliza o compartilhamento de áudio, vídeo, aplicativo e transferência de arquivos para usuários externos.
    
- **Serviço proxy XMPP:** aceita e envia mensagens XMPP (extensible messaging and presence protocol) de e para parceiros federados XMPP configurados.
    
Usuários externos autorizados podem usar seus Servidores de Borda para se conectar à sua implantação interna do Skype for Business Server, mas, caso contrário, eles não fornecem outro acesso à sua rede interna para ninguém.
  
> [!NOTE]
> Os Servidores de Borda são implantados para fornecer conexões para clientes habilitados do Skype for Business e outros Servidores de Borda (em cenários de federação). Você não pode se conectar de outros tipos de cliente ou servidor de ponto de extremidade. O servidor gateway XMPP pode permitir conexões com parceiros XMPP configurados. Mas, novamente, esses são os únicos tipos de cliente e federação que funcionarão. 

> [!NOTE]
> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.
  
### <a name="reverse-proxies"></a>Proxies reversos
<a name="ReverseProxies"> </a>

Um servidor de proxy reverso (RP) não tem função do Skype for Business Server, mas é um componente essencial de uma implantação do Servidor de Borda. Um proxy reverso permite que os usuários externos:
  
- conectar-se a reuniões ou conferências discdas usando URLs simples.
    
- baixe o conteúdo da reunião.
    
- expanda grupos de distribuição.
    
- obter certificados baseados no usuário para autenticação baseada em certificado do cliente
    
- baixe arquivos do Servidor do Address Book ou envie consultas para o serviço de Consulta à Web do Address Book.
    
- obter atualizações de software de cliente e dispositivo.
    
E para dispositivos móveis:
  
- ele permite que eles descubram automaticamente servidores front-end que oferecem serviços de mobilidade.
    
- ele permite notificações por push do Microsoft 365 ou Office 365 para dispositivos móveis.
    
Nossas recomendações de proxy reverso atuais podem ser encontradas na página [Infraestrutura de Telefonia do Skype for Business.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) Portanto, seu proxy reverso:
  
- deve ser capaz de usar a segurança da camada de transporte (TLS) introduzida em seu ambiente por meio de certificados públicos para se conectar aos serviços Web externos publicados de:
    
  - Diretor ou pool de Diretores
    
  - Servidor front-end ou pool de front-end
    
- precisa ser capaz de publicar sites internos usando certificados para criptografia ou publicá-los por meio de meios não criptografados, se necessário.
    
- deve ser capaz de publicar um site hospedado internamente externamente usando um nome de domínio totalmente qualificado (FQDN).
    
- precisa ser capaz de publicar todo o conteúdo do seu site hospedado. Por padrão, você pode usar a diretiva _, que é reconhecida pela maioria dos servidores Web para significar "Publicar todo o **/\\** conteúdo no servidor Web". Você também pode modificar a diretiva por exemplo, _*/Uwca/ \\* *_, que significa "Publicar todo o conteúdo sob o diretório virtual Ucwa".
    
- deve exigir conexões TLS com clientes que solicitam conteúdo de seu site publicado.
    
- tem que aceitar certificados com entradas san (nome alternativo da assunto).
    
- precisa ser capaz de permitir a associação de um certificado a um ouvinte ou interface através da qual o FQDN de serviços Web externos resolverá. As configurações de ouvinte são preferíveis às interfaces. Muitos ouvintes podem ser configurados em uma única interface.
    
- deve permitir a configuração da manipulação de header de host. Frequentemente, o título do host original enviado pelo cliente solicitante deve ser passado transparentemente, em vez de ser modificado pelo proxy reverso.
    
- deve permitir a ponte do tráfego TLS de uma porta definida externamente (por exemplo, TCP 443) para outra porta definida (por exemplo, TCP 4443). Seu proxy reverso pode descriptografar o pacote no recebimento e criptografar o pacote ao enviar.
    
- deve permitir a ponte de tráfego TCP não criptografado de uma porta (por exemplo, TCP 80) para outra (por exemplo, TCP 8080).
    
- precisa permitir a configuração, ou aceitar, autenticação NTLM, sem autenticação e autenticação de passagem.
    
Se o proxy reverso puder atender a todas as necessidades dessa lista, você deve estar à sua frente, mas tenha em mente nossas recomendações no link fornecido acima.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Você precisa colocar sua implantação de Borda atrás de um firewall externo, mas recomendamos ter dois firewalls, um externo e outro interno entre o ambiente de Borda e seu ambiente interno. Toda a nossa documentação em nossos Cenários terá dois firewalls. Recomendamos dois firewalls porque ele garante um roteamento estrito de uma borda de rede para a outra e duplica a proteção de firewall para sua rede interna.
  
### <a name="directors"></a>Diretores
<a name="Directors"> </a>

Esta é uma função opcional. Pode ser um único servidor ou um pool de servidores executando a função de Diretor. É uma função encontrada no ambiente interno do Skype for Business Server.
  
O Diretor é um servidor de próximo salto interno que recebe tráfego SIP de entrada dos Servidores de Borda destinados aos servidores internos do Skype for Business Server. Ele pré-autentica solicitações de entrada e as redireciona para o pool ou servidor de residência de um usuário. Essa pré-autenticação permite que você solte solicitações de conta de usuário não identificadas.
  
Por que isso importa? Uma função importante para um Diretor é proteger servidores Standard Edition e Servidores Front End ou pools de Front End contra tráfego mal-intencionado, como ataques de Negação de Serviço (DoS). Se sua rede estiver inundada com tráfego externo inválido, o tráfego será interrompido no Diretor.
  
### <a name="load-balancers"></a>Balanceadores de Carga
<a name="LoadBalancers"> </a>

A topologia de Borda consolidada dimensionada do Skype for Business Server é otimizada para balanceamento de carga DNS para novas implantações, e recomendamos isso. Se você precisar de alta disponibilidade, recomendamos usar um balanceador de carga de hardware para uma situação específica:
  
- UM do Exchange para usuários remotos usando UM do Exchange _ *anterior** ao Exchange 2013.
    
> [!IMPORTANT]
> É essencial observar que não é possível misturar balanceadores de carga. Em seu ambiente do Skype for Business Server, todas as interfaces devem usar DNS ou HLB. 
  
> [!NOTE]
> Nat de DSR (retorno de servidor direto) não é suportado para o Skype for Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos do balanceador de carga de hardware para Servidores de Borda de Servidores de Borda executando o serviço de Borda A/V

Para qualquer Servidor de Borda que executa o serviço de Borda A/V, estes são os requisitos:
  
- Desativar o nagling de TCP para portas internas e externas 443 (nagling é o processo de combinação de vários pacotes pequenos em um único pacote maior para uma transmissão mais eficiente).
    
- Desativar o nagling TCP para o intervalo de portas externas 50000 - 59999.
    
- Não use NAT em seus firewalls internos ou externos.
    
- Sua interface interna de Borda deve estar em uma rede diferente da interface externa do Servidor de Borda e o roteamento entre elas deve ser desabilitado.
    
- A interface externa de qualquer Servidor de Borda que executa o serviço de Borda A/V deve usar endereços IP publicamente rouáveis e nenhum NAT ou conversão de porta em qualquer um dos endereços IP externos da Borda.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

O Skype for Business Server não tem muitos requisitos de afinidade baseados em cookie. Portanto, você não precisa usar uma persistência baseada em cookie, a menos **que** (e isso seja específico do Skype for Business Server 2015), você terá servidores front-end ou pools de front-end do Lync Server 2010 em seu ambiente do Skype for Business Server. Eles precisariam de afinidade baseada em cookie no método de configuração recomendado para o Lync Server 2010.
  
> [!NOTE]
> Se você decidir ativar a afinidade baseada em cookie para seu HLB, não haverá problema em fazer isso, mesmo que seu ambiente não precise dele. 
  
Se o **seu ambiente não precisar** de afinidade baseada em cookie:
  
- Na regra de publicação de proxy reverso para a porta 443, de definida **Encaminhar o host como** **True**. Isso garantirá que a URL original seja encaminhada.
    
Para implantações que **precisam** de afinidade baseada em cookie:
  
- Na regra de publicação de proxy reverso para a porta 443, de definida **Encaminhar o host como** **True**. Isso garantirá que a URL original seja encaminhada.
    
- O cookie do balanceador de carga de hardware **não deve** ser marcado como httpOnly.
    
- O cookie do balanceador de carga de hardware **não deve ter** um tempo de expiração.
    
- O cookie do balanceador de carga de **hardware** deve ser chamado **de MS-WSMAN** (esse é o valor que os serviços Web esperam e não podem ser alterados).
    
- O cookie do  balanceador de carga de hardware deve ser definido em cada resposta HTTP para a qual a solicitação HTTP de entrada não tinha um cookie, independentemente de uma resposta HTTP anterior nessa mesma conexão TCP ter obtido um cookie. Se o balanceador de carga de hardware otimiza a inserção de cookie para ocorrer apenas uma vez por conexão TCP, essa otimização **não deve** ser usada.
    
> [!NOTE]
> É comum que as configurações de HLB usem afinidade de origem e tempo de vida de sessão TCP de 20 minutos, o que é bom para o Skype for Business Server e seus clientes, pois o estado da sessão é mantido por meio do uso do cliente e/ou interação do aplicativo. 
  
Se você estiver implantando dispositivos móveis, seu HLB deverá ser capaz de balancear a carga de solicitações individuais em uma sessão TCP (na verdade, você precisa ser capaz de balancear a carga de uma solicitação individual com base no endereço IP de destino).
  
> [!IMPORTANT]
> Os HLBs F5 têm um recurso chamado OneConnect. Ele garante que cada solicitação em uma conexão TCP seja balanceada individualmente. Se você estiver implantando dispositivos móveis, verifique se o fornecedor de HLB dá suporte à mesma funcionalidade. Os aplicativos móveis mais recentes do iOS exigem o TLS versão 1.2. Se você precisar saber mais, F5 fornece configurações específicas para isso. 
  
Aqui estão os requisitos de HLB para o Diretor (opcional) e os Serviços Web do pool de front-end (obrigatórios).
  
- Para seus VIPs de Serviços Web internos, Source_addr persistência (porta interna 80, 443) em seu HLB. Para o Skype for Business Server, Source_addr persistência significa que várias conexões provenientes de um único endereço IP são sempre enviadas a um servidor para manter o estado da sessão.
    
- Use um tempo de ociosidade de TCP de 1.800 segundos.
    
- No firewall entre o proxy reverso e o HLB do pool de próximo salto, crie uma regra para permitir o tráfego https: na porta 4443, do proxy reverso para o HLB. Seu HLB precisa ser configurado para ouvir as portas 80, 443 e 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumo dos requisitos de afinidade de HLB

|**Local do cliente/usuário**|**Requisitos de afinidade de FQDN de serviços Web externos**|**Requisitos de afinidade de FQSN de serviços Web internos**|
|:-----|:-----|:-----|
|Skype for Business Web App (usuários internos e externos)  <br/> Dispositivo móvel (usuários internos e externos  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype for Business Web App (somente usuários externos)  <br/> Dispositivo móvel (usuários internos e externos  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype for Business Web App (somente usuários internos)  <br/> Dispositivo móvel (não implantado)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Monitoramento de porta para HLBs

Você define o monitoramento de portas em seus balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis, devido a uma falha de hardware ou comunicação. Por exemplo, se o serviço de Servidor front-end (RTCSRV) parar porque o servidor front-end ou pool de front-end falha, o monitoramento HLB também deve parar de receber tráfego nos Serviços Web. Você deve implementar o monitoramento de porta no HLB para monitorar o seguinte para sua interface externa HLB:
  
|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Nenhum  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Nenhum  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

Abordamos os requisitos de hardware e software do Servidor de Borda em nossos requisitos gerais de servidor para o [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e requisitos de sistema para a documentação do Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="collocation"></a>Collocation

Abordamos a localização do Servidor de Borda em nossa [documentação de Noções Básicas de Topologia do Skype for Business Server.](../../plan-your-deployment/topology-basics/topology-basics.md)
  

