---
title: Lync Server 2013 planejamento de capacidade usando os modelos de usuário
description: Lync Server 2013 planejamento de capacidade usando os modelos de usuário.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b710f7ec88dd75c872d704f2169fa2f161fc186
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544407"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Planejamento de capacidade para Lync Server 2013 usando modelos de usuário

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-01-14_

Esta seção oferece orientação sobre quantos servidores são necessários em um site para o número de usuários desse site, de acordo com o uso descrito em [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Plataforma de hardware testada

Todos os resultados de desempenho e recomendações de implantação nesta seção são baseados nos testes de desempenho em servidores que executam o hardware descrito na tabela a seguir. Recomendamos que você use hardware semelhante. Se você usar hardware menos poderoso, você pode enfrentar problemas de funcionalidade ou mau desempenho. Observe que essas recomendações de hardware são superiores às das versões anteriores do Lync Server.

### <a name="hardware-used-in-performance-testing"></a>Hardware usado em testes de desempenho

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior</p>
<p>Processadores Intel Itanium não são suportados para funções de servidor do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>32 gigabytes (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco.</p>
<p>Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</p>
<p>- Ou</p></li>
<li><p>Drivers de estado sólido (SSDs) que oferecem desempenho semelhante à 8 drivers de disco mecânico de 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que exige agrupamento com um único endereço MAC e um único endereço IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Resumo dos resultados

A tabela a seguir resume essas recomendações.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Função de servidor</th>
<th>Número máximo de usuários suportados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pool de front-ends com doze servidores front-end e um servidor back-end ou um par espelhado de servidores back-end.</p></td>
<td><p>80.000 usuários exclusivos fizeram logon simultaneamente, mais 50% de pontos múltiplos de presença (MPOP) representando instâncias não móveis, mais 40% dos usuários habilitados para mobilidade para um total de 152.000 pontos de extremidade.</p></td>
</tr>
<tr class="even">
<td><p>Conferência A/V</p></td>
<td><p>O serviço de conferência A/V fornecido por um pool de front-ends oferece suporte às conferências do pool, supondo um tamanho máximo de conferência de 250 usuários e apenas uma conferência grande sendo executada de cada vez.</p>
<div>

> [!NOTE]  
> Além disso, você pode dar suporte a conferências grandes de usuários de 250 e 1000 implantando um pool de front-ends separado com dois servidores front-end para hospedar as grandes conferências. Para obter detalhes, consulte <A href="lync-server-2013-supporting-large-meetings.md">Supporting Large encontros using Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Um Servidor de Borda</p></td>
<td><p>12.000 usuários remotos simultâneos</p></td>
</tr>
<tr class="even">
<td><p>Um Diretor</p></td>
<td><p>12.000 usuários remotos simultâneos</p></td>
</tr>
<tr class="odd">
<td><p>Monitoramento e arquivamento</p></td>
<td><p>No Lync Server 2013, os serviços de front-end de monitoramento e arquivamento agora são executados em cada servidor de front-end, em vez de em funções de servidor separadas.</p>
<p>O monitoramento e o arquivamento cada ainda exigem seus próprios repositórios de bancos de dados. Se você também executar o Exchange 2013, poderá manter seus dados de arquivamento no Exchange, em vez de em um banco de dados SQL dedicado.</p></td>
</tr>
<tr class="even">
<td><p>Um Servidor de Mediação</p></td>
<td><p>O servidor de mediação colocado com o servidor front-end é executado em todos os servidores front-end em um pool e deve fornecer capacidade suficiente para os usuários no pool. Para o servidor de mediação autônomo, consulte a seção "servidor de mediação" mais adiante neste tópico.</p></td>
</tr>
<tr class="odd">
<td><p>Um servidor Standard Edition</p></td>
<td><p>É altamente recomendável que, se você usar servidores Standard Edition para hospedar usuários, sempre use dois servidores, emparelhados usando as recomendações de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</a>. Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá suportar 5.000 usuários em um cenário de failover.</p>
<p>Se sua implantação inclui uma quantidade significativa de tráfego de áudio ou vídeo, o desempenho do servidor pode ser prejudicado com mais de 2.500 usuários por servidor. Nesse caso, você deve considerar a adição de servidores Standard Edition ou a migração para o Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Servidor Front-End

<div>


> [!NOTE]  
> Não há suporte para pools estendidos para esta função de servidor.



</div>

Em um pool de front-ends, você deve ter um servidor front-end para cada 6.660 usuários hospedados no pool, supondo que o Hyper-Threading esteja habilitado em todos os servidores do pool e que o hardware do servidor atenda às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md). O número máximo de usuários em um pool de front-ends é 80.000, supondo que o Hyper-Threading esteja habilitado em todos os servidores do pool. Se houver mais de 80.000 usuários em um site, é possível implantar mais de um pool de Front End.

Ao contar o número de usuários em um pool de Front End, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a este pool de Front End.

Quando um servidor ativo fica indisponível, suas conexões são transferidas automaticamente para os outros servidores no pool. Por exemplo, se você tiver 30.000 usuários e cinco servidores front-end, se um servidor não estiver disponível, as conexões de 6000 usuários precisam ser transferidas para os outros quatro servidores. Os quatro servidores restantes terão 7500 usuários, o que é um número maior do que o recomendado.

Se, em vez disso, você começou com seis servidores front-end para os seus usuários 30.000 e, posteriormente, um se tornou indisponível, um total de 5000 usuários será movido para os cinco servidores restantes. Esses cinco servidores serão cada host 6000 usuários, que está no intervalo recomendado.

O número máximo de usuários em um pool de Front End é 80.000. O número máximo de servidores front-end em um pool é 12.

Para um pool de front-ends com 80.000 usuários, doze servidores front-end são suficientes para o desempenho, em implantações comuns que seguem os [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md). As implantações projetadas para dar suporte ao failover de recuperação de desastres pressupõem que um máximo de 40.000 usuários possam ser hospedados em cada um dos dois pools de front-ends emparelhados, em que cada pool tenha servidores front-end suficientes para acomodar os usuários em ambos os pools deve que um pool precise ser failover para o outro.

O número de usuários com suporte com bom desempenho por um pool de front-ends específico pode diferir desses números pelos seguintes motivos:

  - O hardware para seus servidores front-end não atende às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - A utilização da sua organização difere de forma significativa dos modelos de usuário, bem como possui um volume consideravelmente maior de tráfego de conferências.

<div>


> [!IMPORTANT]  
> No Lync Server 2013, os bancos de dados de presença agora estão hospedados em servidores front-end, ao contrário do Lync Server 2010 onde estavam hospedados no servidor back-end. Isso significa que o desempenho do disco e a capacidade de seus servidores front-end não devem ser comprometidos das recomendações listadas anteriormente nesta seção e nas <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor do Lync Server 2013</A>, independentemente do número de usuários hospedados por seus servidores front-end.



</div>

A tabela a seguir mostra a largura de banda média para IM e presença, dado o modelo de usuário, conforme definido nos [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Largura de banda média por usuário</th>
<th>Requisitos de largura de banda por servidor front-end com 6.660 usuários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Para melhorar o desempenho de mídia da funcionalidade do servidor de mediação e de conferência a/V alocada em seus servidores front-end, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede em seus servidores front-end. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento no Windows Server 2008" em <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Máximos de Conferência

Dado o modelo de usuário em que 5% dos usuários em um pool podem estar em uma conferência em qualquer momento, um pool de 80.000 usuários poderia ter cerca de 4.000 usuários em conferências de uma só vez. Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes. Não existe um limite rígido para o número real de conferências permitidas e o uso real determina o desempenho real. Por exemplo, se sua organização tem muito mais conferências de modo misto do que as supostas no modelo de usuário, pode ser necessário implantar mais Servidores Front End ou Servidores de Conferência A/V do que as recomendações neste documento. Para obter detalhes sobre as suposições no modelo de usuário, consulte [User Models in Lync Server 2013](lync-server-2013-user-models.md).

O tamanho máximo de conferência compatível hospedado por um pool de front-ends normal do Lync Server 2013 que também hospeda os usuários é de 250 participantes. Enquanto uma conferência de um usuário 250 está acontecendo, o pool ainda oferece suporte a outras conferências, de forma que um total de 5% dos usuários do pool estejam em conferências simultâneas. Por exemplo, em um pool de doze servidores front-end e 80.000 usuários, enquanto a conferência 250-User está acontecendo, o Lync Server oferece suporte a 3.750 outros usuários que participam de conferências menores.

Independentemente do número de usuários hospedados no pool de front-ends ou no servidor Standard Edition, o Lync Server oferece suporte a um mínimo de 125 outros usuários que participam de conferências menores no mesmo pool ou servidor que está hospedando uma conferência de 250 usuários.

Para habilitar conferências entre 250 e 1000 usuários, você pode configurar um pool de front-ends separado apenas para hospedar essas conferências. Este pool de front-ends não hospedará nenhum usuário. Para obter detalhes, consulte [Supporting Large encontros using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Se sua organização tiver muito mais conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end do que as recomendações neste documento (até um limite de 12 FEs). Para obter detalhes sobre as suposições no modelo de usuário, consulte [User Models in Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Servidor de Borda

<div>


> [!NOTE]  
> Não há suporte para pools estendidos para esta função de servidor.



</div>

Você deve implantar um servidor de borda para cada 12.000 usuários remotos que acessarão um site simultaneamente. São recomendados no mínimo dois Servidores de Borda para alta disponibilidade. Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Ao contar o número de usuários para os Servidores de Borda, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.

<div>


> [!NOTE]  
> Para aprimorar o desempenho do serviço de Borda de Conferência A/V em seus Servidores de Borda, você deve habilitar o receive-side scaling (RSS) nos adaptadores de rede em seus Servidores de Borda. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento no Windows Server 2008" em <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

<div>

## <a name="director"></a>Diretor

<div>


> [!NOTE]  
> Não há suporte para pools estendidos para esta função de servidor.



</div>

Se você implantar a função de servidor diretor, recomendamos implantar um diretor para cada 12.000 usuários remotos que acessarão um site simultaneamente. São recomendados no mínimo dois Diretores para alta disponibilidade. Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Ao contar o número de usuários para os Diretores, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.

</div>

<div>

## <a name="mediation-server"></a>Servidor de Mediação

<div>


> [!NOTE]  
> Não há suporte para pools estendidos para esta função de servidor.



</div>

Se você colocar o servidor de mediação com o servidor front-end, o servidor de mediação será executado em todos os servidores front-end no pool e deve fornecer capacidade suficiente para os usuários no pool.

Se você implantar um pool de servidor de mediação autônomo, o número de servidores de mediação a serem implantados depende de vários fatores, incluindo o hardware usado para o servidor de mediação, o número de usuários de VoIP que você tem, o número de pares de gateway que cada pool de servidor de mediação controla, o tráfego de horas de ocupado por esses gateways e a porcentagem de

As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um servidor de mediação pode lidar, supondo que o hardware para os servidores de mediação atenda aos requisitos em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) e que o Hyper-Threading esteja habilitado. Para obter detalhes sobre a escalabilidade do servidor de mediação, consulte [estimativa de uso de voz e tráfego para o Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Todas as tabelas a seguir consideram o uso resumido em [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacidade de servidor de mediação autônomo: 70% de usuários internos, 30% de usuários externos com capacidade de chamada não-bypass (transcodificação de mídia executada pelo servidor de mediação)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware de servidor</th>
<th>Número máximo de chamadas</th>
<th>Número máximo de linhas T1</th>
<th>Número máximo de linhas E1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processador duplo, Hex Core, CPU de 2,26 GHz <strong>com Hyper-Threading desabilitado</strong>, com memória de 32 GB e uma placa de adaptador de rede de duas portas.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Processador dual, Hex Core, 2,26 GHz com hyper-threaded CPU, com memória de 32 GB e uma placa de adaptador de rede de duas portas.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Embora servidores com 32 GB de memória tenham sido usados para testes de desempenho, servidores com 16 GB de memória são suportados para um Servidor de Mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacidade do servidor de mediação (servidor de mediação colocado com o servidor front-end) 70% de usuários internos, 30% de usuários externos, capacidade de chamadas sem desvio (processamento de mídia executado pelo servidor de mediação)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardware de servidor</th>
<th>Número máximo de chamadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processador dual, Hex Core, 2,26 GHz com hyper-threaded CPU, com memória de 32 GB e 2 placas de adaptador de rede de 1 GB.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Esse número é muito menor do que os números para o servidor de mediação autônomo porque o servidor front-end tem que lidar com outros recursos e funções para os usuários do 6600 hospedados nele, além da transcodificação necessária para chamadas de voz.



</div>

<div>


> [!NOTE]  
> Para melhorar o desempenho do servidor de mediação, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede em seus servidores de mediação. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento no Windows Server 2008" em <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

<div>

## <a name="back-end-server"></a>Servidor de Back-End

No Lync Server 2013, os bancos de dados de presença estão localizados nos servidores front-end, e não no servidor back-end. Isso resultou em um requisito muito mais simples para cada servidor back-end no Lync Server 2013, equivalente ao requisito de hardware para o servidor front-end. Compare com isso com o Lync Server 2010, onde o servidor back-end era necessário para ser um servidor muito mais elevado com 25 discos. No entanto, a carga de trabalho dos servidores de back-end ainda não deve atender às recomendações de hardware listadas anteriormente nesta seção e em [plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Para fornecer alta disponibilidade do servidor back-end, recomendamos implantar o espelhamento do servidor. Para obter mais informações, consulte [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Monitoramento e arquivamento

No Lync Server 2013, se você implantar o monitoramento ou arquivamento, a funcionalidade de front end desses serviços é executada nos servidores front-end, em vez de em funções de servidor separadas. O monitoramento e o arquivamento cada ainda usam seu próprio repositório de banco de dados, separado do repositório de back-end. Como alternativa, se você tiver o Exchange 2013 implantado, poderá armazenar dados de arquivamento de mensagens instantâneas no Exchange, em vez de em um repositório SQL dedicado.

A tabela a seguir indica a quantidade de armazenamento de banco de dados necessária por usuário por dia para monitoramento e arquivamento de dados.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>CDR (monitoramento)</strong></p></td>
<td><p><strong>QoE (monitoramento)</strong></p></td>
<td><p><strong>Arquivamento</strong></p></td>
</tr>
<tr class="even">
<td><p>Espaço em disco exigido por usuário por dia</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


A Microsoft utilizou o hardware na tabela a seguir para o servidor de banco de dados para monitoramento e arquivamento durante o teste de desempenho. O teste coletou os dados de dois pools de front-ends, cada um contendo 80.000 usuários.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Hardware usado em testes de desempenho de monitoramento e arquivamento

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior</p></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>48 gigabytes (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><p>unidades de disco rígido de 25 10.000 RPM com 300 GB em cada disco, com a seguinte configuração</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Drive</strong></p></td>
<td><p><strong>Configuração de RAID</strong></p></td>
<td><p><strong>Número de discos</strong></p></td>
</tr>
<tr class="even">
<td><p>Arquivos de dados de banco de dados de CDR, QoE e arquivamento, em uma única unidade</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>Arquivo de log do banco de dados CDR</p></td>
<td><p>1</p></td>
<td><p>duas</p></td>
</tr>
<tr class="even">
<td><p>Arquivo de log do banco de dados QoE</p></td>
<td><p>1</p></td>
<td><p>duas</p></td>
</tr>
<tr class="odd">
<td><p>Arquivo de log do banco de dados de arquivamento</p></td>
<td><p>1</p></td>
<td><p>duas</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que exige agrupamento com um único endereço MAC e um único endereço IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Estimando o uso de voz e o tráfego do Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

