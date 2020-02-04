---
title: Planejamento da capacidade do Lync Server 2013 usando os modelos de usuário
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
ms.openlocfilehash: cd9b3861e4c84b8df7585ad5cfbdfd5a82359282
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Planejamento de capacidade do Lync Server 2013 usando modelos de usuário

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-14_

Esta seção fornece orientação sobre quantos servidores você precisa em um site para o número de usuários nesse site, de acordo com o uso descrito em [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Plataforma de hardware testada

Todos os resultados de desempenho e recomendações de implantação nesta seção são baseados em teste de desempenho em servidores que executam o hardware descrito na tabela a seguir. Recomendamos que você use hardware semelhante. Se usar um hardware menos poderoso, você poderá enfrentar problemas de funcionalidade ou mau desempenho. Observe que essas recomendações de hardware são superiores às versões anteriores do Lync Server.

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
<p>Não há suporte para processadores Intel Itanium para funções de servidor do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>32 gigabytes (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 ou mais discos rígidos de 10.000-RPM com pelo menos 72 GB de espaço livre em disco.</p>
<p>Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</p>
<p>-OR</p></li>
<li><p>Drivers de estado sólido (SSDs) que oferecem desempenho semelhante a 8 drivers de disco mecânico de 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Resumo de Resultados

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
<td><p>80.000 usuários únicos, mais 50% de pontos múltiplos de presença (MPOP) representando instâncias não móveis, mais 40% de usuários ativados para mobilidade de um total de 152.000 pontos de extremidade.</p></td>
</tr>
<tr class="even">
<td><p>Conferência A/V</p></td>
<td><p>O serviço de conferência A/V fornecido por um pool de front-end oferece suporte a conferências do pool presumindo um tamanho máximo de conferência de usuários do 250, e apenas uma dessas grandes conferências sendo executadas ao mesmo tempo.</p>
<div>

> [!NOTE]  
> Além disso, você pode dar suporte a conferências grandes de usuários do 250 e do 1000 implantando um pool de front-end separado com dois servidores front-end para hospedar as conferências grandes. Para obter detalhes, consulte <A href="lync-server-2013-supporting-large-meetings.md">oferecendo suporte a reuniões grandes usando o Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Um servidor de borda</p></td>
<td><p>12.000 usuários remotos simultâneos</p></td>
</tr>
<tr class="even">
<td><p>Um diretor</p></td>
<td><p>12.000 usuários remotos simultâneos</p></td>
</tr>
<tr class="odd">
<td><p>Monitoramento e Arquivamento</p></td>
<td><p>No Lync Server 2013, os serviços de front-end de monitoramento e arquivamento agora são executados em cada servidor front-end, em vez de funções de servidor separadas.</p>
<p>O monitoramento e arquivamento ainda exigem seus próprios armazenamentos de banco de dados. Se você também tiver o Exchange 2013, poderá manter seus dados de arquivamento no Exchange, em vez de em um banco de dados SQL dedicado.</p></td>
</tr>
<tr class="even">
<td><p>Um servidor de mediação</p></td>
<td><p>O servidor de mediação colocado no front-end Server é executado em cada servidor front-end em um pool e deve fornecer capacidade suficiente para os usuários do pool. Para o servidor de mediação autônomo, consulte a seção "servidor de mediação" mais adiante neste tópico.</p></td>
</tr>
<tr class="odd">
<td><p>Um servidor Standard Edition</p></td>
<td><p>É altamente recomendável que, se você usar os servidores de edição padrão para hospedar usuários, sempre use dois servidores, emparelhados usando as recomendações de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planejamento para alta disponibilidade e recuperação de desastres no Lync Server 2013</a>. Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá dar suporte a 5.000 usuários em um cenário de falha.</p>
<p>Se sua implantação inclui um quantidade de tráfego significativa de áudio ou vídeo, o desempenho do servidor pode ser prejudicado com mais de 2.500 usuários por servidor. Nesse caso, você deve considerar adicionar mais servidores de edição padrão ou mover para o Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Servidor Front-End

<div>


> [!NOTE]  
> Pools ampliados não têm suporte para esta função de servidor.



</div>

Em um pool de front-ends, você deve ter um servidor front-end para cada usuário do 6.660 hospedado no pool, pressupondo que a hipersegmentação esteja habilitada em todos os servidores do pool e que o hardware do servidor atenda às recomendações nas [plataformas de hardware do servidor do Lync server 2013](lync-server-2013-server-hardware-platforms.md). O número máximo de usuários em um pool de front-ends é 80.000, pressupondo que o hyperthreading esteja habilitado em todos os servidores do pool. Se você tiver mais de 80.000 usuários em um site, poderá implantar mais de um pool de front-end.

Quando você conta com o número de usuários em um pool Front-end, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a este pool de front-ends.

Quando um servidor ativo está indisponível, suas conexões são transferidas automaticamente para outros serviços no pool. Por exemplo, se você tiver usuários do 30.000 e cinco servidores front-end, então, se um servidor estiver indisponível, as conexões de 6000 usuários precisam ser transferidas para os outros quatro servidores. Os quatro servidores restantes terão todos os usuários do 7500, que é um número maior do que o recomendado.

Se, em vez disso, você começou com seis servidores front end para seus usuários do 30.000 e, subsequentemente, ele se tornou indisponível, um total de 5000 usuários será movido para os cinco servidores restantes. Esses cinco servidores serão todos os usuários do 6000 host, que estão no intervalo recomendado.

O número máximo de usuários em um pool de front-ends é 80.000. O número máximo de servidores front-end em um pool é 12.

Para um pool de front-ends com usuários do 80.000, doze servidores front-end são suficientes para o desempenho, em implantações típicas que seguem os [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md). Implantações projetadas para dar suporte a failover de recuperação de desastres presumindo que um máximo de 40.000 usuários podem ser hospedados em cada um dos dois pools front-ends emparelhados, em que cada pool tenha servidores de front-end suficientes para acomodar os usuários nos dois pools devem ser que um pool precise ser reprovado para o outro.

O número de usuários com suporte com bom desempenho por parte de um pool de front-end específico pode ser diferente dos seguintes números pelos seguintes motivos:

  - O hardware para seus servidores front-ends não atende às recomendações nas [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - O uso da sua organização difere significativamente dos modelos de usuário, como tráfego de conferência significativamente maior.

<div>


> [!IMPORTANT]  
> No Lync Server 2013, os bancos de dados de presença agora são hospedados em servidores front-end, ao contrário do Lync Server 2010 onde eles estavam hospedados no servidor back-end. Isso significa que o desempenho do disco e a capacidade dos seus servidores front-ends não devem ser comprometidos das recomendações listadas anteriormente nesta seção e nas <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor do Lync server 2013</A>, independentemente do número de usuários hospedados pelos seus servidores front-end.



</div>

A tabela a seguir mostra a média de largura de banda para mensagem instantânea e presença, considerando o modelo de usuário, conforme definido nos [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Largura de banda média por usuário</th>
<th>Requisitos de largura de banda por servidor front-end com usuários do 6.660</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Para melhorar o desempenho de mídia da funcionalidade co-localizado de conferência e servidor de mediação em seus servidores front-end, você deve habilitar o RSS (dimensionamento de recebimento) nos adaptadores de rede em seus servidores front-end. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos no redimensionamento do Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>em. Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Máximos de Conferência

Devido ao modelo de usuário de que 5% dos usuários em um pool pode estar em uma conferência a qualquer momento, um pool de usuários do 80.000 pode ter cerca de 4.000 usuários em conferências ao mesmo tempo. Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes. Não há um limite rígido para o número real de conferências permitidas, e o uso real determina o desempenho real. Por exemplo, se a sua organização tiver muitas outras conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end ou servidores de conferência A/V do que as recomendações contidas neste documento. Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).

O tamanho máximo de conferência compatível hospedado por um pool de front-end do Lync Server 2013 que também hospeda usuários é de 250 participantes. Enquanto esta conferência de 250 usuários está acontecendo, o pool ainda suporta outras conferências, de forma que 5% dos usuários do pool estão em conferências simultâneas. Por exemplo, em um pool de doze servidores de front-end e 80.000 usuários, enquanto a conferência de usuário do 250 está acontecendo, o Lync Server oferece suporte a 3.750 outros usuários que participam de conferências menores.

Independentemente do número de usuários hospedados no pool de front-ends ou no servidor Standard Edition, o Lync Server oferece suporte a um mínimo de 125 outros usuários que participam de conferências menores no mesmo pool ou servidor que hospeda uma conferência de usuário do 250.

Para habilitar conferências com os usuários do 250 e do 1000, você pode configurar um pool de front-end separado apenas para hospedar essas conferências. Este pool de front-ends não hospedará nenhum usuário. Para obter detalhes, consulte [oferecendo suporte a reuniões grandes usando o Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Se a sua organização tiver muitas outras conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end do que as recomendações contidas neste documento (até um limite de 12 FEs). Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Servidor de Borda

<div>


> [!NOTE]  
> Pools ampliados não têm suporte para esta função de servidor.



</div>

Você deve implantar um servidor de borda para cada um dos usuários remotos do 12.000, que acessarão um site simultaneamente. Recomendamos, no mínimo, dois servidores de borda para alta disponibilidade. Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações nas [plataformas de hardware do servidor do Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Quando você conta com o número de usuários para os servidores de borda, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a um pool de front-ends neste site.

<div>


> [!NOTE]  
> Para melhorar o desempenho do serviço de borda de conferência A/V em seus servidores de borda, você deve habilitar o recurso de dimensionamento de recebimento (RSS) nos adaptadores de rede dos servidores de borda. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos no redimensionamento do Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>em. Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

<div>

## <a name="director"></a>Diretor

<div>


> [!NOTE]  
> Pools ampliados não têm suporte para esta função de servidor.



</div>

Se você implantar a função de servidor diretor, recomendamos implantar um director para cada um dos usuários remotos do 12.000 que acessarão um site simultaneamente. Recomendamos, no mínimo, dois diretores para alta disponibilidade. Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações nas [plataformas de hardware do servidor do Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Quando você conta com o número de usuários para os directors, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a um pool de front-end neste site.

</div>

<div>

## <a name="mediation-server"></a>Servidor de Mediação

<div>


> [!NOTE]  
> Pools ampliados não têm suporte para esta função de servidor.



</div>

Se você colocar o servidor de mediação com servidor front-end, o servidor de mediação será executado em todos os servidores front-end do pool e deve fornecer capacidade suficiente para os usuários do pool.

Se você implantar um pool autônomo do servidor de mediação, o número de servidores de mediação a serem implantados depende de muitos fatores, incluindo o hardware usado para o servidor de mediação, o número de usuários de VoIP que você tem, o número de pares de gateways que cada pool de servidores de mediação controles, o tráfego de horas ocupados por meio desses gateways e a porcentagem de chamadas com mídia que ignora o servidor de mediação.

As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um servidor de mediação pode manipular, pressupondo que o hardware dos servidores de mediação atenda aos requisitos nas [plataformas de hardware do servidor do Lync server 2013](lync-server-2013-server-hardware-platforms.md) e que o Hyper-Threading esteja habilitado. Para obter detalhes sobre a escalabilidade do servidor de mediação, consulte [estimando o uso de voz e o tráfego do Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) e [diretrizes de implantação do servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Todas as tabelas a seguir consideram o uso resumido nos [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacidade autônoma do servidor de mediação: 70% usuários internos, 30% usuários externos com capacidade de chamada não ignorada (transcodificação de mídia realizada pelo servidor de mediação)

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
<td><p>Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded, <strong>com hyper-threading desabilitado</strong>, com 32 GB de memória e uma placa de adaptador de rede dual-port.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded, com 32 GB de memória e uma placa de adaptador de rede dual-port.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Embora os servidores com 32 GB de memória sejam usados para teste de desempenho, os servidores com 16 GB de memória são compatíveis com o servidor de mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacidade do servidor de mediação (servidor de mediação posicionado com servidor front-end) 70% usuários internos, 30% usuários externos, capacidade de chamada sem bypass (processamento de mídia executado pelo servidor de mediação)

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
<td><p>Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded com hyper-threading e 2 placas de adaptador de rede de 1GB.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Esse número é muito menor do que os números do servidor de mediação autônomo porque o servidor front-end tem de manipular outros recursos e funções para os usuários do 6600 hospedados nele, além da transcodificação necessária para chamadas de voz.



</div>

<div>


> [!NOTE]  
> Para melhorar o desempenho do servidor de mediação, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede em seus servidores de mediação. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos no redimensionamento do Windows Server 2008" <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>em. Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

<div>

## <a name="back-end-server"></a>Servidor Back-End

No Lync Server 2013, os bancos de dados de presença estão localizados nos servidores front-end, em vez do servidor back-end. Isso resultava em um requisito muito mais simples para cada servidor back-end no Lync Server 2013, equivalente ao requisito de hardware para o servidor front-end. Compare isso com o Lync Server 2010, em que o servidor back-end era necessário para ser um servidor de nível muito mais alto com 25 discos. No entanto, a carga de trabalho dos servidores back-end ainda não deve atender às recomendações de hardware listadas anteriormente nesta seção e nas [plataformas de hardware do servidor do Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Para fornecer alta disponibilidade de seu servidor back-end, recomendamos implantar o espelhamento do servidor. Para obter mais informações, consulte [back-end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Monitoramento e Arquivamento

No Lync Server 2013, se você implantar o monitoramento ou o arquivamento, a funcionalidade de front-end desses serviços é executada nos servidores front-end, em vez de nas funções de servidor separadas. Monitorar e arquivar cada um ainda usa seu próprio repositório de banco de dados, separado da loja back-end. Como alternativa, se você tiver o Exchange 2013 implantado, poderá armazenar dados de arquivamento de mensagens instantâneas no Exchange em vez de em um repositório SQL dedicado.

A tabela a seguir indica aproximadamente quanto armazenamento de banco de dados é exigido por usuário, por dia, para os dados de monitoramento e arquivamento.


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
<td><p><strong>CDR (Monitoramento)</strong></p></td>
<td><p><strong>QoE (Monitoramento)</strong></p></td>
<td><p><strong>Archiving</strong></p></td>
</tr>
<tr class="even">
<td><p>Espaço em disco exigido por usuário, por dia</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


A Microsoft usou o hardware na tabela a seguir para p servidor de banco de dados para monitoramento e arquivamento durante seus testes de desempenho. O teste coletou os dados de dois pools de front-end, cada um contendo 80.000 usuários.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Hardware usado nos testes de desempenho de monitoramento e arquivamento

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
<td><p>25 unidades de disco rígido de 10.000-RPM com 300 GB em cada unidade, com a seguinte configuração</p>
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
<td><p><strong>Unidade</strong></p></td>
<td><p><strong>Configuração RAID</strong></p></td>
<td><p><strong>Número de discos</strong></p></td>
</tr>
<tr class="even">
<td><p>CDR, QoE e arquivos de banco de dados de arquivamento, em uma única unidade</p></td>
<td><p>1+0</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>Arquivo de log do banco de dados de CDR</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Arquivo de log do banco de dados de QoE</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Arquivo de log do banco de dados de arquivamento</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Estimando uso e tráfego de voz para Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

