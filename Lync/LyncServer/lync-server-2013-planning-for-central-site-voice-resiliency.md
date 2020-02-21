---
title: 'Lync Server 2013: planejamento para resiliência de voz do site central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a61a07ae14f004b406aa38ef783a1c873f2128
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planejamento da resiliência de voz do site central no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-30_

Cada vez mais, as empresas têm vários locais espalhados em todo o mundo. Manter os serviços de emergência, o acesso ao suporte técnico e a capacidade de conduzir tarefas de negócios críticos quando um site central está fora do serviço é essencial para qualquer solução de resiliência do Enterprise Voice. Quando um site central fica indisponível, as seguintes condições devem ser atendidas:

  - O failover de voz deve ser fornecido.

  - Os usuários que normalmente se registram com o pool de front-ends no site central devem ser capazes de se registrar em um pool de front-ends alternativo. Isso pode ser feito criando vários registros SRV DNS, cada um deles resolve para um pool de diretores ou pool de front-ends em cada um dos seus sites centrais. Você pode ajustar a prioridade e os pesos dos registros SRV para que os usuários que são atendidos por esse site central obtenham o diretor e o pool de front-ends correspondentes em frente dos outros Registros SRV.

  - Chamadas para e de usuários localizados em outros sites devem ser redirecionadas para o PSTN.

Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.

<div>

## <a name="architecture-and-topology"></a>Arquitetura e topologia

O planejamento da resiliência de voz em um site central requer uma compreensão básica da função central desempenhada pelo registrador do Lync Server 2013 para habilitar o failover de voz. O registrador do Lync Server é uma função de servidor que permite o registro e a autenticação de clientes e fornece serviços de roteamento. Ele reside junto com outros componentes em um servidor Standard Edition, servidor front-end, diretor ou aparelho de filial persistente. Um pool de registrador consiste em serviços de registrador em execução no pool de front-ends e residir no mesmo site. O pool de front-ends deve ter o balanceamento de carga. O balanceamento de carga de DNS é recomendado, mas o balanceamento de carga de hardware é aceitável. Um cliente Lync descobre o pool de front-ends através do seguinte mecanismo de descoberta:

1.  Registro SRV de DNS

2.  Serviço Web de descoberta automática (novo no Lync Server 2013)

3.  Opção de DHCP 120

Depois que o cliente do Lync se conecta ao pool de front-ends, ele é direcionado pelo balanceador de carga para um dos servidores front-end no pool. Esse servidor front-end, por sua vez, redireciona o cliente para um registrador preferencial no pool.

Cada usuário habilitado para o Enterprise Voice é atribuído a um determinado pool de registradores, que se torna o pool principal de registradores do usuário. Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de registradores primários. Para considerar o consumo de recursos do site central por qualquer usuário de site de filial que confie no site central para presença, conferência ou failover, recomendamos que você considere cada usuário de site de filial como se o usuário fosse um usuário registrado no site central. No momento, não há limites para o número de usuários do site de filial, incluindo usuários registrados em um aparelho de filial persistente.

Para garantir a resiliência de voz no caso de uma falha de local central, o pool de registradores primário deve ter um único pool de registradores de backup designado, localizado em outro site. O backup pode ser configurado usando as configurações de resiliência do construtor de topologias. Supondo que um link de WAN resiliente entre os dois sites, os usuários cujo pool de registradores primários não está mais disponível são direcionados automaticamente para o pool de registradores de backup.

As etapas a seguir descrevem o processo de descoberta e registro do cliente:

1.  Um cliente descobre o Lync Server por meio de registros DNS SRV. No Lync Server 2013, os registros SRV DNS podem ser configurados para retornar mais de um FQDN para a consulta SRV de DNS. Por exemplo, se a contoso da empresa tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de diretores em cada site central, os registros SRV DNS poderão apontar para os FQDNs do pool de diretores em cada um dos três locais. Contanto que o pool de diretor de um dos locais esteja disponível, o cliente pode se conectar ao primeiro servidor Lync Server.
    
    <div>
    

    > [!NOTE]  
    > O uso de um pool de diretor é opcional. Um pool de front-ends pode ser usado em seu lugar.

    
    </div>

2.  O pool de diretores informa o cliente do Lync sobre o pool de registradores primário e o pool de registradores de backup do usuário.

3.  O cliente Lync tenta se conectar primeiro ao pool de registradores primários do usuário. Se o pool de registradores primário estiver disponível, o registrador aceitará o registro. Se o pool de registradores primários não estiver disponível, o cliente do Lync tentará se conectar ao pool de registradores de backup. Se o pool de registradores de backup estiver disponível e tiver determinado que o pool de registradores primários do usuário não está disponível (detectando a falta de pulsação para um intervalo de failover especificado), o pool de registradores de backup aceita o registro do usuário. Depois que o registrador de backup detectar que o registrador principal está disponível novamente, o pool de registradores de backup redirecionará os clientes do Lync de failover para o pool principal.

A figura a seguir mostra a topologia recomendada para garantir a resiliência do site central. Os dois sites estão conectados por um link WAN resiliente. Se o site central ficar indisponível, os usuários atribuídos a esse pool serão direcionados para o site de backup para registro.

**Topologia recomendada para a resiliência de voz do site central**

![Topologia para resiliência de voz do site central](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologia para resiliência de voz do site central")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Os seguintes requisitos e recomendações para implementar a resiliência de voz do site central são apropriados para a maioria das organizações:

  - Os sites nos quais residem os pools de registradores primário e de backup devem estar conectados por um link WAN resiliente.

  - Cada site central deve conter um pool de registradores que consiste em um ou mais registradores.

  - Cada pool de registradores deve ter balanceamento de carga usando o balanceamento de carga DNS, balanceamento de carga de hardware ou ambos. Para obter informações detalhadas sobre como planejar a configuração de balanceamento de carga, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Cada usuário deve ser atribuído a um pool de registradores primário usando o cmdlet **set-CsUser** do Lync Server Management Shell ou o painel de controle do Lync Server.

  - O pool de registradores primário deve ter um único pool de registradores de backup localizado em um site central diferente.

  - O pool de registradores primário deve ser configurado para fazer failover para o pool de registradores de backup. Por padrão, o registrador principal é definido para failover para o pool de registradores de backup após um intervalo de 300 segundos. Você pode alterar esse intervalo usando o construtor de topologias do Lync Server 2013.

  - Configure uma rota de failover, conforme descrito no tópico "[Configurando uma rota de failover no Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)", na documentação de planejamento. Ao configurar a rota, especifique um gateway que esteja localizado em um site diferente do gateway especificado na rota principal.

  - Se o site central contiver o servidor de gerenciamento principal e se o site for provavelmente inoperante por um período estendido, será necessário reinstalar as ferramentas de gerenciamento no local de backup; caso contrário, você não poderá alterar as configurações de gerenciamento.

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
<td><p><strong>Funcionamento</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Resolvendo Registros SRV e registros de servidor-servidor e servidor-cliente</p></td>
</tr>
<tr class="odd">
<td><p>Exchange e serviços Web do Exchange (EWS)</p></td>
<td><p>Armazenamento de contatos; dados de calendário</p></td>
</tr>
<tr class="even">
<td><p>Unificação de mensagens do Exchange e serviços Web do Exchange</p></td>
<td><p>Logs de chamada, lista de caixa postal, caixa postal</p></td>
</tr>
<tr class="odd">
<td><p>Opções de DHCP 120</p></td>
<td><p>Se o DNS SRV não estiver disponível, o cliente tentará usar a opção 120 de DHCP para descobrir o registrador. Para que isso funcione, é necessário configurar um servidor DHCP ou o Lync Server 2013 DHCP deve estar habilitado. Para obter detalhes, consulte requisitos de hardware e software para resiliência de site de filial na seção <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site para Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Recursos de voz persistente

Se os requisitos e as recomendações anteriores tiverem sido implementados, os seguintes recursos de voz serão fornecidos pelo pool de registradores de backup:

  - Chamadas PSTN de saída

  - Chamadas PSTN de entrada, se o provedor de serviços de telefonia oferecer suporte à capacidade de failover para um site de backup

  - Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes

  - Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

  - Mensagens instantâneas de dois participantes e compartilhamento de áudio e vídeo entre usuários no mesmo site

  - Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se as duas partes da delegação de chamada ou todos os membros da equipe estiverem configuradas no mesmo site.

  - Os clientes e telefones existentes continuam funcionando.

  - CDR (registro de detalhes das chamadas)

  - Autenticação e autorização

Dependendo de como estão configurados, os seguintes recursos de voz podem ou não funcionar quando um site central primário está fora de serviço:

  - Depósito e recuperação de caixa postal
    
    Se você quiser tornar o UM do Exchange disponível quando o site central primário estiver fora de serviço, você deve executar um dos seguintes procedimentos:
    
      - Altere os registros SRV DNS para que os servidores UM do Exchange no site central apontem para os servidores de backup do UM do Exchange em outro site.
    
      - Configure o plano de discagem de UM de cada usuário para incluir os servidores de UM do Exchange no site central e no site de backup, mas designe os servidores de backup de UM do Exchange como desabilitado. Se o site primário ficar indisponível, o administrador do Exchange precisará marcar os servidores de UM do Exchange no local de backup como habilitados.
    
    Se nenhuma das soluções anteriores for possível, a UM do Exchange não estará disponível, caso o site central fique indisponível.

  - Conferência de todos os tipos
    
    Um usuário com failover em um site de backup pode ingressar em uma conferência que é criada ou hospedada por um organizador cujo pool está disponível, mas não pode criar ou hospedar uma conferência em seu próprio pool principal, o que não está mais disponível. Da mesma forma, outros usuários não podem participar de conferências hospedadas no pool principal do usuário afetado.

Os seguintes recursos de voz não funcionam quando um site central primário está fora de serviço:

  - Atendedor automático de conferência

  - Presença e roteamento baseado em DND

  - Atualização de configurações de encaminhamento de chamadas

  - Serviço de grupo de resposta e estacionamento de chamada

  - Provisionamento de novos telefones e clientes

  - Pesquisa na Web do catálogo de endereços

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de resiliência de voz no site de filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

