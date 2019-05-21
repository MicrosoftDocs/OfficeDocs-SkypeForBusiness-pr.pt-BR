---
title: Requisitos do sistema do servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Resumo: Saiba mais sobre os requisitos do sistema para o servidor de borda no Skype for Business Server.'
ms.openlocfilehash: 01a5cce8dd1ccb85d322b6c66615d022c8d6c2df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277143"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos do sistema do servidor de borda no Skype for Business Server
 
**Resumo:** Saiba mais sobre os requisitos do sistema para o Edge Server no Skype for Business Server.
  
Quando se trata de sua implantação do servidor de borda do Skype for Business Server, essas são as coisas que você precisará fazer para o servidor ou servidores que estão no próprio ambiente, bem como planejar a estrutura do ambiente. Para obter mais informações sobre topologia, DNS, certificados e outras preocupações de infraestrutura, verifique a documentação de requisitos do ambiente.
  
## <a name="components"></a>Componentes

Ao discutir o ambiente do servidor de borda, estamos fazendo referência a componentes que são, na maioria das vezes, implantados em uma rede de perímetro (isso significa que ele está em um grupo de trabalho ou em um domínio fora da estrutura de domínio do Skype for Business Server).
  
Com isso em mente, esses são os componentes nos quais você deverá prestar atenção para implantar sua Borda com êxito:
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (são opcionais e, se forem incluídos, ficarão localizados em sua rede interna)
    
- [Balanceadores de carga](system-requirements.md#LoadBalancers) (você pode ter o balanceamento de carga de DNS ou um balanceador de carga de hardware (HLB), mas para um único servidor de borda, isso não é necessário)
    
Temos mais detalhes sobre cada um abaixo:
  
### <a name="edge-servers"></a>Servidores de Borda
<a name="EdgeServers"> </a>

Estes são os servidores do Skype for Business implantados em seu ambiente de perímetro. Sua função é enviar e receber tráfego de rede para usuários externos para os serviços oferecidos pela implantação interna do Skype for Business Server. Para fazer isso com êxito, cada servidor de borda executa:
  
- **Serviço de borda de acesso**: fornece um ponto de conexão confiável e único para tráfego de protocolo de iniciação de sessão (SIP) de entrada e saída.
    
- **Serviço de borda**de Webconferência: permite que usuários externos ingressem em reuniões hospedadas em seu ambiente interno do Skype for Business Server.
    
- **O serviço de borda A/V**: torna o compartilhamento de áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos disponíveis para usuários externos.
    
- **XMPP proxy Service**: aceita e envia mensagens de protocolo de presença e mensagens de protocolo de presença (XMPP) de e para os parceiros federados XMPP configurados.
    
Usuários externos autorizados podem usar seus servidores de borda para se conectar à implantação interna do Skype for Business Server, mas, caso contrário, não fornecerão nenhum outro acesso à sua rede interna para qualquer pessoa.
  
> [!NOTE]
> Os servidores de borda são implantados para fornecer conexões para clientes do Skype for Business habilitados e outros servidores de borda (em cenários de Federação). Não é possível se conectar de outros tipos de servidor ou clientes de ponto de extremidade. O servidor de Gateway XMPP pode permitir conexões com parceiros XMPP configurados. Mas, mais uma vez, esses são os únicos tipos de federação e cliente que funcionam. 

> [!NOTE]
> Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [migrando a Federação do XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.
  
### <a name="reverse-proxies"></a>Proxies reversos
<a name="ReverseProxies"> </a>

Um servidor de proxy reverso (RP) não tem função de servidor do Skype for Business, mas é um componente essencial de uma implantação de servidor de borda. Um proxy reverso permite que os usuários externos:
  
- conectem-se às reuniões ou conferências discadas usando URLs simples.
    
- baixem o conteúdo da reunião.
    
- expandam grupos de distribuição.
    
- obtenham certificados com base no usuário para autenticação com base no certificado do cliente
    
- baixar arquivos do servidor de catálogo de endereços ou enviar consultas para o serviço de consulta à Web do catálogo de endereços.
    
- obtenham atualizações para software de dispositivo e cliente.
    
E, para dispositivos móveis:
  
- Ele permite que eles descubram automaticamente os servidores front-end que oferecem serviços de mobilidade.
    
- Ele permite notificações por push do Office 365 para dispositivos móveis.
    
Nossas recomendações atuais de proxy inverso podem ser encontradas na [infraestrutura de telefonia da página do Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Para seu proxy reverso:
  
- deve estar apto a utilizar o protocolo TLS introduzido em seu ambiente por meio de certificados públicos para se conectar com os serviços da Web externos publicados do:
    
  - Pool de directors ou diretor
    
  - Servidor front-end ou pool de front-end
    
- deve ser capaz de publicar sites Web internos pelo uso de certificados para criptografia ou publicá-los por um meio não criptografado, se necessário.
    
- deve ser capaz de publicar externamente um site Web hospedado internamente, pelo uso de um nome de domínio totalmente qualificado (FQDN).
    
- deve ser capaz de publicar todos os conteúdos do site da Web hospedado. Por padrão, você pode usar a ** / **diretiva *, que é reconhecida pela maioria dos servidores Web, para significar "publicar todo o conteúdo no servidor Web". Você também pode modificar a diretiva — por exemplo, * */Uwca/\\* * *, que significa "publicar todo o conteúdo sob o diretório virtual Ucwa".
    
- deve exigir conexões TLS com clientes que solicitam conteúdo de seu site da Web publicado.
    
- deve aceitar certificados com entradas de nomes de entidade alternativos (SAN).
    
- deve ser capaz de permitir associação de um certificado a um ouvinte ou interface pela qual os serviços Web externos FQDN se resolverão. Configurações de ouvinte são preferíveis para interfaces. Muitos ouvintes podem ser configurados em uma única interface.
    
- deve permitir a configuração de gerenciamento de cabeçalho do host. Geralmente, o cabeçalho original do host enviado pelo cliente solicitante deve ser passado de forma transparente, em vez de ser modificado pelo proxy reverso.
    
- deve permitir ponte do tráfego SSL e TLS a partir de uma porta definida externamente (por exemplo, TCP 443) para outra porta definida (por exemplo, TCP 4443). Seu proxy reverso pode descriptografar o pacote no recebimento e criptografar novamente o pacote no envio.
    
- deve permitir ponte de tráfego TCP não criptografado a partir de uma porta (por exemplo, TCP 80) para outra (por exemplo, TCP 8080).
    
- deve permitir (ou aceitar) a configuração da autenticação de NTLM, sem autenticação e autenticação de passagem.
    
Se o seu proxy reverso puder atender a todas as necessidades desta lista, você deve estar em trânsito, mas lembre-se das nossas recomendações no link fornecido acima.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Você precisa colocar a implantação de Borda por trás de um firewall externo, mas recomendamos ter dois firewalls: um externo e um interno entre o ambiente da Borda e seu ambiente interno. Toda a documentação de nossos Cenários terá dois firewalls. Recomendamos dois firewalls, pois isso garante o roteamento estrito de uma borda de rede para a outra e duplica a proteção de firewall para a sua rede interna.
  
### <a name="directors"></a>Diretores
<a name="Directors"> </a>

Esta é uma função opcional. Pode ser um único servidor ou um pool de servidores que executam a função de diretor. É um papel encontrado no ambiente do Skype for Business Server interno.
  
O diretor é um servidor de próximo salto interno que recebe o tráfego SIP de entrada dos servidores de borda destinados a servidores internos do Skype for Business Server. Ele pré-autentica as solicitações de entrada e as redireciona para o pool inicial do usuário ou servidor. Essa pré-autenticação permite ignorar solicitações de contas de usuário não identificadas.
  
Por que isso importa? Uma função importante para um diretor é proteger servidores de edição padrão e servidores front-end ou pools de front-end contra tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a sua rede estiver inundada com tráfego externo inválido, o tráfego será interrompido no diretor.
  
### <a name="load-balancers"></a>Balanceadores de Carga
<a name="LoadBalancers"> </a>

A topologia de borda consolidada do Skype for Business Server dimensionada é otimizada para o balanceamento de carga de DNS para novas implantações e recomendamos isso. Se precisar de alta disponibilidade, recomendamos o uso de um balanceador de carga de hardware para uma situação específica:
  
- Exchange UM para usuários remotos usando o Exchange UM **antes** do Exchange 2013.
    
> [!IMPORTANT]
> É importante observar que não é possível misturar balanceadores de carga. Em seu ambiente do Skype for Business Server, todas as interfaces devem usar DNS ou o HLB. 
  
> [!NOTE]
> O NAT do Direct Server Return (DSR) não é compatível com o Skype for Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos do balanceador de carga de hardware para servidores Edge Edge servidores que executam o serviço de borda A/V

Para qualquer servidor de borda executando o serviço de borda A/V, estes são os requisitos:
  
- Desative o nagling de TCP para as portas interna e externa 443. Nagling é o processo de combinação de diversos pacotes pequenos em um único pacote maior para uma transmissão mais eficiente.
    
- Desative o nagling de TCP para o intervalo de portas externas 50000 a 59999.
    
- Não use NAT em seus firewalls internos ou externos.
    
- Sua interface interna de borda deve estar em uma rede diferente do que a interface externa do servidor de borda, e o roteamento entre elas deve ser desativado.
    
- A interface externa de qualquer servidor de borda que executa o serviço de borda A/V deve usar endereços IP roteáveis publicamente e sem NAT ou conversão de porta em qualquer um dos endereços IP externos de borda.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

O Skype for Business Server não tem muitos requisitos de afinidade baseados em cookies. Portanto, você não precisa usar uma persistência baseada em cookies **, a não ser** que (e esta seja a do Skype for business Server 2015 específica) você tenha servidores de front-end do Lync Server 2010 ou pools front-end no ambiente do Skype for Business Server. Eles precisariam de afinidade baseada em cookies no método de configuração recomendado para o Lync Server 2010.
  
> [!NOTE]
> Se você decidir ativar a afinidade com base em cookies em seu HLB, não haverá problema, mesmo se não for necessário para seu ambiente. 
  
Se seu ambiente **não** precisar de afinidade baseada em cookies:
  
- Na regra de publicação de proxy reverso para a porta 443, defina **encaminhar cabeçalho do host** como **verdadeiro**. Isso garantirá que a URL original seja encaminhada.
    
Para implantações que **precisarão** de afinidade baseada em cookies:
  
- Na regra de publicação de proxy reverso para a porta 443, defina **encaminhar cabeçalho do host** como **verdadeiro**. Isso garantirá que a URL original seja encaminhada.
    
- O cookie de balanceador de carga de hardware **não deve** ser marcado como httpOnly.
    
- O cookie de balanceador de carga de hardware **não deve** ter um período de expiração.
    
- O cookie de balanceamento de carga de hardware **deve** ser nomeado **MS-WSMan** (esse é o valor que os serviços Web esperam e não pode ser alterado).
    
- O cookie de balanceador de carga de hardware **deve** ser definido em cada resposta http para a qual a solicitação HTTP de entrada não tenha um cookie, independentemente de uma resposta http anterior na mesma conexão TCP ter recebido um cookie. Se o balanceador de carga de hardware otimizar a inserção de cookies para ocorrer apenas uma vez por conexão TCP, essa otimização **não deve** ser usada.
    
> [!NOTE]
> É típico para configurações de HLB usar a afinidade de origem e a vida útil da sessão TCP de 20 minutos, o que é muito bom para o Skype for Business Server e seus clientes, porque o estado da sessão é mantido por meio do uso do cliente e/ou da interação do aplicativo. 
  
Se estiver implantando dispositivos móveis, o HLB deverá ser capaz de balancear a carga das solicitações individuais em uma sessão TCP (na verdade, você deve poder balancear a carga de uma solicitação individual com base no endereço IP de destino).
  
> [!IMPORTANT]
> Os HLBs F5 têm um recurso chamado OneConnect que assegura que todas as solicitações de uma conexão TCP tenham a carga balanceada individualmente. Se estiver implantando dispositivos móveis, verifique se o fornecedor do HLB tem o mesmo recurso. Os aplicativos móveis mais recentes do iOS exigem a versão 1.2 do protocolo TLS. Se você precisar de mais informações, o F5 oferece configurações específicas para isso. 
  
Estes são os requisitos de HLB para o diretor (opcional) e (obrigatório) serviços Web de pool de front-end:
  
- Para seus VIPs internos de serviços Web, defina persistência Source_addr (porta interna 80, 443) em seu HLB. Para o Skype for Business Server, Source_addr persistência significa que várias conexões provenientes de um único endereço IP são sempre enviadas para um servidor, para manter o estado da sessão.
    
- Use um tempo de ociosidade de TCP de 1.800 segundos.
    
- No firewall entre seu proxy reverso e o próximo HLB do pool de saltos, crie uma regra para permitir https: o tráfego na porta 4443, do seu proxy reverso para seu HLB. O HLB deve ser configurado para ouvir as portas 80, 443 e 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumo dos requisitos de afinidade HLB

|**Local do cliente/usuário**|**Requisitos de afinidade de FQDN de serviços Web externos**|**Requisitos de afinidade de FQDN de serviços Web internos**|
|:-----|:-----|:-----|
|Skype for Business Web App (usuários internos e externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype for Business Web App (somente usuários externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype for Business Web App (somente usuários internos)  <br/> Dispositivo móvel (não implantado)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Monitoramento de portas nos HLBs

Você define o monitoramento de porta em seus balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis, devido à falha de hardware ou de comunicações. Por exemplo, se o serviço do servidor front-end (RTCSRV) parar porque o servidor front-end ou o pool de front-end falha, o monitoramento HLB também deve parar de receber tráfego nos serviços Web. Implante o monitoramento de portas no HLB para monitorar o seguinte em sua interface externa do HLB:
  
|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs\>de pool  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs\>de pool  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

Abordamos os requisitos de hardware e software do Edge Server em nossos [requisitos gerais do servidor para o Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [requisitos do sistema para a documentação do Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Colocação

Abordamos a localização do servidor de borda em nossas [noções básicas de topologia para a documentação do Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

