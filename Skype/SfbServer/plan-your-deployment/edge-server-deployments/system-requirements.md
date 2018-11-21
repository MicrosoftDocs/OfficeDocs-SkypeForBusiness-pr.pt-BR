---
title: Requisitos de sistema do servidor de borda no Skype para Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Resumo: Saiba mais sobre os requisitos de sistema para o servidor de borda no Skype para Business Server.'
ms.openlocfilehash: 16cc2a5e640872fe8c57113c7aaca588efab121a
ms.sourcegitcommit: ff0c4bef4d4cbc71d51fce941aff63739a0016e9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2018
ms.locfileid: "26626157"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos de sistema do servidor de borda no Skype para Business Server
 
**Resumo:** Saiba mais sobre os requisitos de sistema para o servidor de borda no Skype para Business Server.
  
Quando se trata de sua Skype para implantação de servidor de borda do servidor de negócios, essas são as coisas que você precisará fazer para o servidor ou servidores que estão no ambiente do próprio, bem como planejar a estrutura do ambiente. Para obter mais informações sobre topologia, DNS, certificados e outras preocupações de infraestrutura, verifique a documentação de requisitos do ambiente.
  
## <a name="components"></a>Componentes

Ao discutir o ambiente de servidor de borda, estamos fazendo referência componentes, na maioria das vezes, implantados em uma rede de perímetro (ou seja, quer dizer que ele está em um grupo de trabalho ou um domínio que está fora da sua Skype para a estrutura de domínio do servidor de negócios).
  
Com isso em mente, esses são os componentes nos quais você deverá prestar atenção para implantar sua Borda com êxito:
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (são opcionais e, se forem incluídos, ficarão localizados em sua rede interna)
    
- [Balanceadores de carga](system-requirements.md#LoadBalancers) (você pode ter o balanceamento de carga DNS ou um balanceador de carga de hardware (HLB), mas para um único servidor de borda, isso não é necessário)
    
Temos mais detalhes sobre cada um abaixo:
  
### <a name="edge-servers"></a>Servidores de Borda
<a name="EdgeServers"> </a>

Estes são o Skype para servidores de negócios implantado em seu ambiente de perímetro. Suas funções é enviar e receber tráfego de rede para usuários externos para os serviços oferecidos pelo seu Skype interno para implantação de servidor de negócios. Para fazer isso com êxito, cada servidor de borda executa:
  
- **Serviço de borda de acesso**: fornece um ponto de conexão único e confiável para o tráfego de protocolo de iniciação de sessão (SIP) de entrada e de saída.
    
- **Serviço de borda de webconferência**: permite que os usuários externos ingressem em reuniões hospedadas em sua Skype interno para ambiente de servidor de negócios.
    
- **Uma / serviço de borda V**: torna o áudio, vídeo, compartilhamento de aplicativos e disponíveis para usuários externos de transferência de arquivo.
    
- **Serviço de Proxy XMPP**: aceita e envia mensagens (XMPP) de protocolo de presença e mensagens extensível de e para parceiros federados XMPP configurados.
    
Os usuários externos autorizados podem usar os servidores de borda para se conectar ao seu Skype interno para implantação de servidor de negócios, mas caso contrário, eles fornecem nenhum outro acesso à sua rede interna para qualquer pessoa.
  
> [!NOTE]
> Servidores de borda são implantados para fornecer conexões para Skype habilitado para clientes de negócios e outros servidores de borda (em cenários de federação). Não é possível se conectar de outros tipos de servidor ou clientes de ponto de extremidade. O servidor de Gateway XMPP pode permitir conexões com parceiros XMPP configurados. Mas, mais uma vez, esses são os únicos tipos de federação e cliente que funcionam. 

> [!NOTE]
> Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019. Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.
  
### <a name="reverse-proxies"></a>Proxies reversos
<a name="ReverseProxies"> </a>

Um servidor proxy reverso (RP) não tem nenhuma Skype para a função de servidor de negócios, mas é um componente essencial de uma implantação de servidor de borda. Um proxy reverso permite que os usuários externos:
  
- conectem-se às reuniões ou conferências discadas usando URLs simples.
    
- baixem o conteúdo da reunião.
    
- expandam grupos de distribuição.
    
- obtenham certificados com base no usuário para autenticação com base no certificado do cliente
    
- Baixe arquivos do servidor de catálogo de endereço ou enviem consultas ao serviço Address Book Web Query.
    
- obtenham atualizações para software de dispositivo e cliente.
    
E, para dispositivos móveis:
  
- permite que eles descobrir automaticamente os servidores Front-End que oferece serviços de mobilidade.
    
- Ele permite que as notificações por push do Office 365 para dispositivos móveis.
    
Nossas recomendações de proxy reverso atual podem ser encontradas na página de [Infraestrutura de telefonia para Skype para negócios](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Portanto seu proxy reverso:
  
- deve estar apto a utilizar o protocolo TLS introduzido em seu ambiente por meio de certificados públicos para se conectar com os serviços da Web externos publicados do:
    
  - Diretor ou pool de diretores
    
  - Pool de Front End Server ou Front-End
    
- deve ser capaz de publicar sites Web internos pelo uso de certificados para criptografia ou publicá-los por um meio não criptografado, se necessário.
    
- deve ser capaz de publicar externamente um site Web hospedado internamente, pelo uso de um nome de domínio totalmente qualificado (FQDN).
    
- deve ser capaz de publicar todos os conteúdos do site da Web hospedado. Por padrão, você pode usar o ** / *** diretiva, que é reconhecida pela maioria dos servidores web para significar "Publicar todo o conteúdo no servidor web". Você também pode modificar a diretiva — por exemplo, * * /Uwca/\\* * *, que significa "publica todo o conteúdo sob o diretório virtual Ucwa."
    
- deve exigir conexões TLS com clientes que solicitam conteúdo de seu site da Web publicado.
    
- deve aceitar certificados com entradas de nomes de entidade alternativos (SAN).
    
- deve ser capaz de permitir associação de um certificado a um ouvinte ou interface pela qual os serviços Web externos FQDN se resolverão. Configurações de ouvinte são preferíveis para interfaces. Muitos ouvintes podem ser configurados em uma única interface.
    
- deve permitir a configuração de gerenciamento de cabeçalho do host. Muitas vezes, o cabeçalho de host original enviado pelo cliente solicitante deve ser passado transparente, em vez de sendo modificado pelo proxy reverso.
    
- deve permitir ponte do tráfego SSL e TLS a partir de uma porta definida externamente (por exemplo, TCP 443) para outra porta definida (por exemplo, TCP 4443). Seu proxy reverso pode descriptografar o pacote no recebimento e, em seguida, criptografe novamente o pacote em enviar.
    
- deve permitir ponte de tráfego TCP não criptografado a partir de uma porta (por exemplo, TCP 80) para outra (por exemplo, TCP 8080).
    
- deve permitir (ou aceitar) a configuração da autenticação de NTLM, sem autenticação e autenticação de passagem.
    
Se seu proxy reverso possa ser resolvidos todas as necessidades nessa lista, você deve estar bom ir, mas tenha em mente nossas recomendações no link acima.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Você precisa colocar a implantação de Borda por trás de um firewall externo, mas recomendamos ter dois firewalls: um externo e um interno entre o ambiente da Borda e seu ambiente interno. Toda a documentação de nossos Cenários terá dois firewalls. Recomendamos dois firewalls, pois isso garante o roteamento estrito de uma borda de rede para a outra e duplica a proteção de firewall para a sua rede interna.
  
### <a name="directors"></a>Diretores
<a name="Directors"> </a>

Esta é uma função opcional. Pode ser um único servidor ou um pool de servidores que executam a função Diretor. É uma função encontrada no Skype interno para ambiente de servidor de negócios.
  
O diretor é um servidor de salto próximo interno que recebe o tráfego SIP de entrada os servidores de borda destinado a Skype para servidores internos do servidor de negócios. Ele pré-autentica as solicitações de entrada e as redireciona para o pool inicial do usuário ou servidor. Essa pré-autenticação permite ignorar solicitações de contas de usuário não identificadas.
  
Por que isso importa? Uma função importante para um diretor é proteger os servidores Standard Edition e servidores Front-End ou pools de Front-End contra tráfego malicioso, como ataques (dos negação) de negação de serviço. Se a sua rede é inundada com tráfego externo inválido, o tráfego para no diretor.
  
### <a name="load-balancers"></a>Balanceadores de Carga
<a name="LoadBalancers"> </a>

O Skype para topologia de borda consolidada do servidor de negócios em escala é otimizada para novas implantações de balanceamento de carga do DNS e recomendamos isso. Se você precisar de alta disponibilidade, recomendamos o uso de um balanceador de carga de hardware para uma situação específica:
  
- UM do Exchange para usuários remotos que usam UM do Exchange **anterior** para o Exchange 2013.
    
> [!IMPORTANT]
> É importante observar que não é possível misturar balanceadores de carga. Em seu Skype para ambiente de servidor de negócios todas as interfaces devem usar DNS ou HLB. 
  
> [!NOTE]
> Servidor direto retornar NAT do (DSR) não é compatível com Skype para Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos do balanceador de carga de hardware para servidores de borda de servidores de borda executando A / serviço de borda V

Para qualquer servidor de borda executando A / serviço de borda V, estes são os requisitos:
  
- Desative o nagling de TCP para as portas interna e externa 443. Nagling é o processo de combinação de diversos pacotes pequenos em um único pacote maior para uma transmissão mais eficiente.
    
- Desative o nagling de TCP para o intervalo de portas externas 50000 a 59999.
    
- Não use NAT em seus firewalls internos ou externos.
    
- Sua interface interna de borda deve estar em uma rede diferente sua interface externa do servidor de borda e roteamento entre elas deve ser desabilitado.
    
- A interface externa de qualquer servidor de borda executando A / serviço de borda de V deve usar endereços IP publicamente roteáveis e não NAT ou conversão de porta em qualquer um dos endereços IP externos borda.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

Skype para Business Server não tem muitos dos requisitos de afinidade baseada em cookie. Para que você não precisa usar a persistência baseada em cookie **, a menos que** (e isso é Skype para servidor 2015 específicos de negócios) você vai ter pools de Front-End ou de Front End Servers do Lync Server 2010 em sua Skype para ambiente de servidor de negócios. Eles precisaria afinidade baseada em cookie no método configuração recomendada para o Lync Server 2010.
  
> [!NOTE]
> Se você decidir ativar a afinidade com base em cookies em seu HLB, não haverá problema, mesmo se não for necessário para seu ambiente. 
  
Se seu ambiente **não** precisar de afinidade baseada em cookies:
  
- Na regra publicação de proxy reverso para a porta 443, defina o **cabeçalho de host Forward** como **True**. Isso garantirá que a URL original seja encaminhada.
    
Para implantações que **precisarão** de afinidade baseada em cookies:
  
- Na regra publicação de proxy reverso para a porta 443, defina o **cabeçalho de host Forward** como **True**. Isso garantirá que a URL original seja encaminhada.
    
- O hardware load balanceador cookie **não deve** ser marcados httpOnly.
    
- O hardware load balanceador cookie **não deve** ter um tempo de expiração.
    
- O hardware load balanceador cookie **deve** ser nomeado **MS-WSMAN** (Este é o valor que os serviços Web esperam e não pode ser alterado).
    
- O hardware load balanceador cookie **deve** ser definida em cada resposta HTTP para o qual a solicitação HTTP de entrada não tinha um cookie, independentemente se uma resposta HTTP anterior nessa mesma conexão de TCP tivessem um cookie. Se seu balanceador de carga de hardware otimiza o cookie insert para que ela ocorra somente uma vez por conexão TCP, esse otimização **não deve** ser usado.
    
> [!NOTE]
> É comum para configurações de HLB usar a afinidade de origem e 20 minuto TCP ciclo de vida de sessão, que é bom para Skype para o servidor de negócios e seus clientes, pois o estado de sessão é mantido por meio do uso do cliente e/ou a interação do aplicativo. 
  
Se estiver implantando dispositivos móveis, o HLB deverá ser capaz de balancear a carga das solicitações individuais em uma sessão TCP (na verdade, você deve poder balancear a carga de uma solicitação individual com base no endereço IP de destino).
  
> [!IMPORTANT]
> Os HLBs F5 têm um recurso chamado OneConnect que assegura que todas as solicitações de uma conexão TCP tenham a carga balanceada individualmente. Se estiver implantando dispositivos móveis, verifique se o fornecedor do HLB tem o mesmo recurso. Os aplicativos móveis mais recentes do iOS exigem a versão 1.2 do protocolo TLS. Se você precisar de mais informações, o F5 oferece configurações específicas para isso. 
  
Aqui estão os requisitos de HLB para o Diretor (opcional) e o pool de Front-End (obrigatório) serviços da Web:
  
- Para sua VIPs de serviços Web internos, defina Source_addr persistência (porta interna 80, 443) em seu HLB. Para Skype para Business Server, a persistência de Source_addr significa que várias conexões provenientes de um único endereço IP sempre são enviadas para um servidor, para manter o estado da sessão.
    
- Use um tempo de ociosidade de TCP de 1.800 segundos.
    
- No firewall entre seu proxy reverso e HLB do seu pool do próximo salto, criar uma regra para permitir o https: o tráfego na porta 4443, do seu proxy reverso para sua HLB. O HLB deve ser configurado para ouvir as portas 80, 443 e 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumo dos requisitos de afinidade HLB

|**Local do cliente/usuário**|**Requisitos de afinidade de FQDN de serviços Web externos**|**Requisitos de afinidade de FQDN de serviços Web internos**|
|:-----|:-----|:-----|
|Skype para negócios Web App (usuários internos e externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype para negócios Web App (apenas para usuários externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype para negócios Web App (apenas para usuários internos)  <br/> Dispositivo móvel (não implantado)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Monitoramento de portas nos HLBs

Você definir o monitoramento de portas nos seus balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis devido a falha de hardware ou communications. Por exemplo, se o serviço de servidor Front-End (RTCSRV) parar porque o servidor Front-End ou Front End pool falha, o monitoramento de HLB deve também parar de receber tráfego dos serviços Web. Implante o monitoramento de portas no HLB para monitorar o seguinte em sua interface externa do HLB:
  
|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

Falamos sobre requisitos de hardware e software do servidor de borda em nossa documentação de [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [requisitos de sistema do Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) geral.
  
## <a name="collocation"></a>Colocação

Abordamos colocação do servidor de borda em nossa documentação [Noções básicas de topologia para Skype para Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

