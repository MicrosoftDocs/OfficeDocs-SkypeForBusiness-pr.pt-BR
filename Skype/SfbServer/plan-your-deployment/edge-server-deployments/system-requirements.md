---
title: Requisitos de sistema do servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: Saiba mais sobre os requisitos do sistema para o servidor de borda no Skype for Business Server.'
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221021"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos de sistema do servidor de borda no Skype for Business Server
 
**Resumo:** Saiba mais sobre os requisitos do sistema para o servidor de borda no Skype for Business Server.
  
Quando se trata de sua implantação do servidor de borda do Skype for Business Server, essas são as coisas que você precisará fazer para o servidor ou servidores que estão no próprio ambiente, bem como o planejamento da estrutura do ambiente. Para obter mais informações sobre topologia, DNS, certificados e outras preocupações de infra-estrutura, confira a documentação de requisitos de ambiente.
  
## <a name="components"></a>Componentes

Ao abordar o ambiente do servidor de borda, estamos fazendo referência a componentes que são, para a maior parte, implantados em uma rede de perímetro (isso significa que eles estão em um grupo de trabalho ou um domínio fora da estrutura de domínio do Skype for Business Server).
  
Tendo isso em mente, estes são os componentes que você precisará ter em mente para implantar sua borda com êxito:
  
- [Servidores de borda](system-requirements.md#EdgeServers)
    
- [Proxies reversos](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Diretores](system-requirements.md#Directors) (são opcionais e, se estiverem incluídos, eles estarão localizados em sua rede interna)
    
- [Balanceadores de carga](system-requirements.md#LoadBalancers) (você pode ter o balanceamento de carga DNS ou um balanceador de carga de hardware (HLB), mas para um único servidor de borda, isso não é necessário)
    
Temos mais detalhes em cada um dos seguintes:
  
### <a name="edge-servers"></a>Servidores de Borda
<a name="EdgeServers"> </a>

Estes são os servidores do Skype for Business implantados no ambiente de perímetro. Sua função é enviar e receber tráfego de rede para usuários externos para os serviços oferecidos pela implantação interna do Skype for Business Server. Para fazer isso com êxito, cada servidor de borda é executado:
  
- **Serviço de borda de acesso**: fornece um ponto de conexão único e confiável para o tráfego do protocolo SIP (Session Initiation Protocol) de entrada e saída.
    
- **Serviço de borda de Webconferência**: permite que usuários externos ingressem em reuniões hospedadas em seu ambiente interno do Skype for Business Server.
    
- **Serviço de borda A/V**: disponibiliza áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos para usuários externos.
    
- **XMPP proxy Service**: aceita e envia mensagens de XMPP (Extensible Messaging and Presence Protocol) de e para parceiros federados XMPP configurados.
    
Usuários externos autorizados podem usar seus servidores de borda para se conectar à sua implantação interna do Skype for Business Server, mas, caso contrário, não fornecerão nenhum outro acesso à sua rede interna para qualquer pessoa.
  
> [!NOTE]
> Os servidores de borda são implantados para fornecer conexões para clientes do Skype for Business habilitados e outros servidores de borda (em cenários de Federação). Você não pode se conectar de outros tipos de cliente ou de servidor de ponto de extremidade. O servidor de gateway do XMPP pode permitir conexões com parceiros do XMPP configurados. Mas, novamente, esses são os únicos tipos de cliente e de Federação que funcionarão. 

> [!NOTE]
> Os gateways e proxies do XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.
  
### <a name="reverse-proxies"></a>Proxies reversos
<a name="ReverseProxies"> </a>

Um servidor de proxy reverso (RP) não tem função do Skype for Business Server, mas é um componente essencial de uma implantação de servidor de borda. Um proxy reverso permite que usuários externos:
  
- Conecte-se a reuniões ou conferências discadas usando URLs simples.
    
- baixar o conteúdo da reunião.
    
- Expanda grupos de distribuição.
    
- obter certificados baseados no usuário para autenticação baseada em certificado de cliente
    
- baixar arquivos do servidor de catálogo de endereços ou enviar consultas para o serviço de consulta à Web do catálogo de endereços.
    
- Obtenha atualizações para software cliente e de dispositivo.
    
E para dispositivos móveis:
  
- Ele permite que eles descubram automaticamente os servidores front-end que oferecem serviços de mobilidade.
    
- Ele habilita as notificações por push do Microsoft 365 ou do Office 365 para dispositivos móveis.
    
Nossas recomendações de proxy reverso atuais podem ser encontradas na página [infraestrutura de telefonia para o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Portanto, seu proxy reverso:
  
- deve ser capaz de usar a segurança de camada de transporte (TLS) introduzida no seu ambiente por meio de certificados públicos para se conectar aos serviços Web externos publicados do:
    
  - Diretor ou pool de diretor
    
  - Servidor front-end ou pool de front-ends
    
- o precisa ser capaz de publicar sites internos usando certificados para criptografia ou publicá-los por um meio não criptografado, se necessário.
    
- deve ser capaz de publicar um site da Web hospedado internamente por meio de um FQDN (nome de domínio totalmente qualificado).
    
- o precisa ser capaz de publicar todo o conteúdo do seu site da Web hospedado. Por padrão, você pode usar a **/\\** diretiva *, que é reconhecida pela maioria dos servidores Web para significar "publicar todo o conteúdo no servidor Web". Você também pode modificar a diretiva — por exemplo, * */Uwca/ \\ * * *, que significa "publicar todo o conteúdo sob o diretório virtual Ucwa."
    
- deve exigir conexões TLS com clientes que solicitam conteúdo do seu site publicado.
    
- deve aceitar certificados com entradas de nome alternativo de entidade (SAN).
    
- o precisa ser capaz de permitir a associação de um certificado a um ouvinte ou uma interface por meio da qual o FQDN de serviços Web externos resolverá. As configurações de escuta são preferidas para interfaces. Muitos ouvintes podem ser configurados em uma única interface.
    
- deve permitir a configuração do controle de cabeçalho de host. Geralmente, o cabeçalho de host original enviado pelo cliente solicitante deve ser passado de forma transparente, em vez de ser modificado pelo proxy reverso.
    
- deve permitir a ponte de tráfego TLS de uma porta definida externamente (por exemplo, TCP 443) para outra porta definida (por exemplo, TCP 4443). Seu proxy reverso pode descriptografar o pacote no recebimento e, em seguida, criptografar novamente o pacote no envio.
    
- deve permitir a ponte de tráfego TCP não criptografado de uma porta (por exemplo, TCP 80) para outra (por exemplo, TCP 8080).
    
- precisa permitir a configuração ou aceitar a autenticação NTLM, sem autenticação e autenticação de passagem.
    
Se o seu proxy reverso puder atender a todas as necessidades desta lista, você deve estar pronto, mas lembre-se das nossas recomendações no link fornecido acima.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Você precisa colocar a implantação de borda por trás de um firewall externo, mas recomendamos ter dois firewalls, um externo e um interno entre o ambiente de borda e seu ambiente interno. Toda nossa documentação em nossos cenários terá dois firewalls. Recomendamos dois firewalls porque ele garante um roteamento estrito de uma borda de rede para o outro e dobra a proteção de firewall para a sua rede interna.
  
### <a name="directors"></a>Director
<a name="Directors"> </a>

Esta é uma função opcional. Pode ser um único servidor ou um pool de servidores que executam a função diretor. É uma função encontrada no ambiente interno do Skype for Business Server.
  
O diretor é um servidor de próximo salto interno que recebe o tráfego SIP de entrada dos servidores de borda destinados aos servidores internos do Skype for Business Server. Ele autentica solicitações de entrada e as redireciona para o pool ou servidor de casa de um usuário. Essa pré-autenticação permite que você remova solicitações de conta de usuário não identificadas.
  
Por que isso importa? Uma função importante para um diretor é proteger servidores Standard Edition e servidores front-end ou pools de front-ends de tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se sua rede estiver inundada com tráfego externo inválido, o tráfego para no diretor.
  
### <a name="load-balancers"></a>Balanceadores de carga
<a name="LoadBalancers"> </a>

A topologia de borda consolidada dimensionada do Skype for Business Server é otimizada para o balanceamento de carga de DNS para novas implantações e recomendamos isso. Se você precisar de alta disponibilidade, recomendamos o uso de um balanceador de carga de hardware para uma situação específica:
  
- UM do Exchange para usuários remotos usando o UM do Exchange **antes** do Exchange 2013.
    
> [!IMPORTANT]
> É vital observar que não é possível misturar balanceadores de carga. No ambiente do Skype for Business Server, todas as interfaces devem usar o DNS ou o HLB. 
  
> [!NOTE]
> O NAT de retorno direto de servidor (DSR) não tem suporte para o Skype for Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos do balanceador de carga de hardware para servidores de borda servidores de borda executando o serviço de borda A/V

Para qualquer servidor de borda executando o serviço de borda A/V, estes são os requisitos:
  
- Desative o TCP nagling para portas internas e externas 443 (nagling é o processo de combinar vários pacotes pequenos em um único pacote maior para uma transmissão mais eficiente).
    
- Desative o nagling de TCP para o intervalo de porta externa 50000-59999.
    
- Não use o NAT em seus firewalls internos ou externos.
    
- Sua interface interna de borda deve estar em uma rede diferente da interface externa do servidor de borda e o roteamento entre elas deve estar desabilitado.
    
- A interface externa de qualquer servidor de borda executando o serviço de borda A/V deve usar endereços IP roteáveis publicamente e sem NAT ou conversão de porta em qualquer um dos endereços IP externos de borda.
    
#### <a name="hlb-requirements"></a>Requisitos do HLB

O Skype for Business Server não tem muitos requisitos de afinidade com base em cookies. Portanto, você não precisa usar uma persistência baseada em cookie **, a não ser** que (e isso seja o Skype for Business Server 2015-específico) você tenha servidores front-end do Lync Server 2010 ou pools de front-end no seu ambiente do Skype for Business Server. Eles precisariam de afinidade com base em cookies no método de configuração recomendado para o Lync Server 2010.
  
> [!NOTE]
> Se você decidir ativar a afinidade com base em cookies para o seu HLB, não haverá um problema fazendo isso, mesmo que seu ambiente não precise dela. 
  
Se seu ambiente **não** precisa de afinidade baseada em cookies:
  
- Na regra de publicação de proxy reverso para a porta 443, defina **encaminhar cabeçalho de host** como **verdadeiro**. Isso garantirá que a URL original seja encaminhada.
    
Para implantações **que precisam de afinidade** com base em cookies:
  
- Na regra de publicação de proxy reverso para a porta 443, defina **encaminhar cabeçalho de host** como **verdadeiro**. Isso garantirá que a URL original seja encaminhada.
    
- O cookie do balanceador de carga de hardware **não deve** ser marcado como httpOnly.
    
- O cookie do balanceador de carga de hardware **não deve** ter um tempo de expiração.
    
- O cookie do balanceador de carga de hardware **deve** ser nomeado como **MS-WSMan** (esse é o valor que os serviços Web esperam e não pode ser alterado).
    
- O cookie do balanceador de carga de hardware **deve** ser definido em cada resposta http para a qual a solicitação HTTP de entrada não tenha um cookie, independentemente de uma resposta http anterior na mesma conexão TCP ter chegado a um cookie. Se o balanceador de carga de hardware otimiza a inserção de cookie para apenas uma vez por conexão TCP, essa otimização **não deve** ser usada.
    
> [!NOTE]
> É normal que as configurações do HLB usem a afinidade de origem e a duração da sessão TCP de 20 minutos, o que é muito bom para o Skype for Business Server e seus clientes, pois o estado da sessão é mantido por meio do uso do cliente e/ou interação de aplicativos. 
  
Se você estiver implantando dispositivos móveis, seu HLB deve ser capaz de carregar as solicitações individuais de balanceamento dentro de uma sessão TCP (na verdade, você precisará ser capaz de carregar o balanceamento de carga de uma solicitação individual com base no endereço IP de destino).
  
> [!IMPORTANT]
> F5 HLBs têm um recurso chamado OneConnect. Ele garante que cada solicitação em uma conexão TCP tenha balanceamento de carga individualmente. Se você estiver implantando dispositivos móveis, verifique se o seu fornecedor de HLB oferece suporte à mesma funcionalidade. Os aplicativos móveis iOS mais recentes exigem a versão 1,2 do TLS. Se você precisar saber mais, F5 fornecerá configurações específicas para isso. 
  
Estes são os requisitos do HLB para o diretor (opcional) e (obrigatório) serviços Web do pool Front-end:
  
- Para seus VIPs de serviços Web internos, defina Source_addr persistência (porta interna 80, 443) no seu HLB. Para o Skype for Business Server, Source_addr persistência significa que várias conexões provenientes de um único endereço IP são sempre enviadas a um servidor para manter o estado da sessão.
    
- Use um tempo limite de ociosidade de TCP de 1800 segundos.
    
- No firewall entre o proxy reverso e o HLB do pool de próximo salto, crie uma regra para permitir https: o tráfego na porta 4443, do seu proxy reverso para o HLB. Seu HLB precisa ser configurado para escutar nas portas 80, 443 e 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumo dos requisitos de afinidade do HLB

|**Local do cliente/usuário**|**Requisitos de afinidade de FQDN de serviços Web externos**|**Requisitos de afinidade de FQDN de serviços Web internos**|
|:-----|:-----|:-----|
|Skype for Business Web App (usuários internos e externos)  <br/> Dispositivo móvel (usuários internos e externos  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype for Business Web App (apenas usuários externos)  <br/> Dispositivo móvel (usuários internos e externos  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Skype for Business Web App (somente usuários internos)  <br/> Dispositivo móvel (não implantado)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Monitoramento de porta para HLBs

Você define o monitoramento de portas nos balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis devido a uma falha de hardware ou comunicação. Por exemplo, se o serviço de servidor front-end (RTCSRV) parar porque o servidor front-end ou o pool de front-ends falha, o monitoramento do HLB também deve parar de receber tráfego nos serviços Web. Você deve implementar o monitoramento de portas no HLB para monitorar o seguinte para a interface externa do HLB:
  
|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs de pool \>  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Nenhum  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs de pool \>  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Nenhum  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

Abordamos os requisitos de hardware e software do servidor de borda em nossos [requisitos gerais de servidor para o Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [a documentação dos requisitos do sistema para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Colocação

Abordamos a colocação do servidor de borda em nossas [noções básicas de topologia para a documentação do Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

