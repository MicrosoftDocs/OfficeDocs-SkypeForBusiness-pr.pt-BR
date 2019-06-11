---
title: 'Lync Server 2013: Planejamento de resiliência de voz do site central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planejamento de resiliência de voz do site central no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-30_

Cada vez mais, as empresas possuem vários sites espalhados por todo o mundo. A manutenção de serviços de emergência, o acesso ao suporte técnico e a capacidade de conduzir tarefas essenciais para empresas quando um site central está fora do serviço é essencial para qualquer solução de resiliência de voz corporativa. Quando um site central torna-se indisponível, as seguintes condições devem ser atendidas:

  - O failover de voz deve ser fornecido.

  - Os usuários que normalmente se registram com o pool de front-end no site central devem ser capazes de se registrar com um pool de front-end alternativo. Isso pode ser feito criando vários registros SRV DNS, cada um deles resolve para um pool de directors ou um pool de front-end em cada um dos seus sites centrais. Você pode ajustar a prioridade e os pesos dos registros SRV para que os usuários que são servidos por esse site central obtenham o diretor e o pool de front-end correspondentes à frente daqueles em outros Registros SRV.

  - As chamadas para/de usuários localizados em outros sites devem ser reencaminhadas para a PSTN.

Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.

<div>

## <a name="architecture-and-topology"></a>Arquitetura e topologia

Planejar a resiliência de voz em um site central requer uma compreensão básica da função central executada pelo registrador do Lync Server 2013 para habilitar o failover de voz. O registrador do Lync Server é uma função de servidor que permite registro e autenticação de cliente e fornece serviços de roteamento. Ele reside juntamente com outros componentes em um servidor Standard Edition, servidor front-end, diretor ou aparelho para filiais sobreviventes. Um pool de registrador consiste em serviços de registrador em execução no pool de front-ends e no mesmo site. O pool de front-ends deve ser de balanceamento de carga. O balanceamento de carga de DNS é recomendado, mas o balanceamento de carga de hardware é aceitável. Um cliente do Lync descobre o pool de front-ends por meio do seguinte mecanismo de descoberta:

1.  Registro SRV de DNS

2.  Serviço Web de descoberta automática (novo no Lync Server 2013)

3.  Opção 120 do DHCP

Depois que o cliente do Lync se conecta ao pool de front-end, ele é direcionado pelo balanceador de carga para um dos servidores de front-end do pool. Esse servidor front-end, por sua vez, redireciona o cliente para um registrador preferencial no pool.

Cada usuário habilitado para o Enterprise Voice é atribuído a um pool de registrador específico, que se torna o pool de registradores primários do usuário. Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de Registradores Avançados primário. Para calcular o consumo de recursos do site central pelos usuários do site de filial que dependem do site central para presença, conferência ou failover, recomendamos considerar cada usuário do site de filial como se fosse um usuário registrado no site central. No momento, não há limites quanto ao número de usuários de sites de filiais, incluindo usuários registrados em um aparelho de ramificação sobreviventes.

Para garantir a resiliência de voz em caso de uma falha do site central, o pool de Registradores Avançados primário deve ter um único pool de Registradores Avançados de backup designado localizado em outro site. O backup pode ser configurado usando as configurações de resiliência do construtor de topologia. Supondo que haja um link WAN resiliente entre os dois sites, os usuários cujo pool de Registradores Avançados primário não está mais disponível serão direcionados automaticamente para pool de backup.

As etapas a seguir descrevem o processo de descoberta e registro de clientes:

1.  Um cliente descobre o Lync Server por meio de registros SRV DNS. No Lync Server 2013, os registros SRV DNS podem ser configurados para retornar mais de um FQDN para a consulta SRV DNS. Por exemplo, se a empresa Contoso tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de Diretores em cada um desses sites, os registros DNS SRV poderão apontar para os FQDNs do pool de Diretores em cada um dos três locais. Desde que o pool do diretor em um dos locais esteja disponível, o cliente pode se conectar ao primeiro servidor do Lync.
    
    <div>
    

    > [!NOTE]  
    > Usar um pool de diretor é opcional. Um pool de front-ends pode ser usado em vez disso.

    
    </div>

2.  O pool de directors informa ao cliente do Lync sobre o pool de registradores primários do usuário e o pool de registrador de backup.

3.  O cliente do Lync tenta se conectar ao pool de registradores primários do usuário primeiro. Se esse pool estiver disponível, o Registrador Avançado aceitará o registro. Se o pool de registradores primários não estiver disponível, o cliente do Lync tentará se conectar ao pool de registradores de backup. Se esse pool estiver disponível e tiver verificado que o pool primário do usuário não está disponível (detectando a falta de pulsação durante um intervalo especificado de failover), o pool de backup aceitará o registro do usuário. Após o registrador de backup detectar que o registrador principal está disponível novamente, o pool de registrador de backup redirecionará os clientes do Lync de failover para o pool primário.

A figura a seguir mostra a topologia recomendada para garantir a resiliência do site central. Os dois sites são conectados por um link de WAN resistente. Se o site central ficar indisponível, os usuários atribuídos a esse pool serão direcionados para o site de backup para a inscrição.

**Topologia recomendada para resiliência de voz do site central**

![Topologia para resliency de voz do site central] (images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologia para resliency de voz do site central")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Os seguintes requisitos e recomendações para a implementação da resiliência de voz do site central são apropriados para a maioria das organizações:

  - Os sites nos quais residem os pools de Registradores Avançados primário e de backup devem estar conectados por um link WAN resiliente.

  - Cada site central deve conter um pool de Registradores Avançados que consiste em um ou mais Registradores Avançados.

  - Cada pool de Registradores Avançados deve ter sua carga balanceada por meio do balanceamento de carga DNS, do balanceamento de carga de hardware ou de ambos. Para obter informações detalhadas sobre como planejar a configuração de balanceamento de carga, consulte [requisitos de balanceamento de carga para o Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Cada usuário deve ser atribuído a um pool principal de registradores usando o cmdlet **set-CsUser** do Shell de gerenciamento do Lync Server ou o painel de controle do Lync Server.

  - O pool primário deve ter um único pool de backup localizado em um site central diferente.

  - O pool de Registradores Avançados primário deve ser configurado de modo que seja feito o seu failover para o pool de Registradores Avançados de backup. Por padrão, o Registrador primário é definido para que esse failover ocorra após um intervalo de 300 segundos. Você pode alterar esse intervalo usando o construtor de topologias do Lync Server 2013.

  - Configure uma rota de failover, conforme descrito no tópico "Configurando[uma rota de failover no Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" na documentação de planejamento. Ao configurar a rota, especifique um gateway que está localizado em um site diferente do gateway especificado na rota primária.

  - Se o site central contiver o servidor de gerenciamento principal, e seja provável que esse site fique inoperante por um longo período, você precisará reinstalar suas ferramentas de gerenciamento no site de backup; caso contrário, você não poderá alterar nenhuma das configurações de gerenciamento.

</div>

<div>

## <a name="dependencies"></a>Dependências

O Lync Server depende dos seguintes componentes de infraestrutura e software para garantir a resiliência de voz:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Componente</strong></p></td>
<td><p><strong>Funcional</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Resolver registros SRV e registros A para conectividade de servidor-servidor e servidor-cliente</p></td>
</tr>
<tr class="odd">
<td><p>Exchange e Serviços Web do Exchange (EWS)</p></td>
<td><p>Armazenamento de contatos; dados do calendário</p></td>
</tr>
<tr class="even">
<td><p>Unificação de Mensagens do Exchange e Serviços Web do Exchange</p></td>
<td><p>Logs de chamada, lista de caixas postais, caixa postal</p></td>
</tr>
<tr class="odd">
<td><p>Opções 120 do DHCP</p></td>
<td><p>Se o DNS SRV não estiver disponível, o cliente tentará usar a Opção 120 do DHCP para descobrir o Registrador Avançado. Para que isso funcione, um servidor DHCP deve ser configurado ou o Lync Server 2013 DHCP deve estar habilitado. Para obter detalhes, consulte requisitos de hardware e software para resiliência de site de filial na seção <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site para o Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Recursos de voz persistente

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
    
    Um usuário que fez failover para um site de backup pode ingressar em uma conferência criada ou hospedada por um organizador cujo pool está disponível, mas não pode criar nem hospedar uma conferência no seu próprio pool primário, que não está mais disponível. Da mesma forma, outros usuários não podem ingressar em conferências hospedadas no pool primário do usuário afetado.

Os seguintes recursos de voz não funcionam quando um site central primário está fora de serviço:

  - Atendedor Automático de Conferência

  - Roteamento baseado em DND e presença

  - Atualização de configurações de encaminhamento de chamadas

  - Serviço de Grupo de Resposta e Estacionamento de Chamada

  - Provisionamento de novos telefones e clientes

  - Pesquisa do Catálogo de Endereços na Web

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de resiliência de voz no site da filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

