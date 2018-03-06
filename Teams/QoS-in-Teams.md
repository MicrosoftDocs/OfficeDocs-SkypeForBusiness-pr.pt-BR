---
title: "Qualidade de Serviço (QoS) no Microsoft Teams"
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 02/16/2018
ms.topic: article
ms.service: msteams
description: "Prepare a rede da sua organização para a Qualidade de Serviço (QoS) no Microsoft Teams"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 61bebd64c7d1478c16e114631b696dee2bf59625
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="quality-of-service-qos-in-microsoft-teams"></a>Qualidade de Serviço (QoS) no Microsoft Teams
==========================================
Este guia ajudará na preparação da rede da sua organização para a Qualidade de Serviço (QoS) no Microsoft Teams.


A Qualidade de Serviço (QoS) é um mecanismo que permite priorizar determinados tipos de tráfego de rede. A priorização do tráfego de serviços de comunicação em tempo real, como o Microsoft Teams, é importante para oferecer uma experiência do usuário em nível corporativo. Para que a QoS seja realmente efetiva, é necessário configurar uma conexão compatível com QoS de ponta a ponta (computadores, comutadores de rede e roteadores para a nuvem), pois se não houver suporte à QoS em alguma parte do caminho, a qualidade de toda a chamada poderá ser reduzida.


![Captura de tela de um diagrama que ilustra a relação entre as redes de uma organização e os serviços do Office 365.](media/Qos-in-Teams-Image1.png)

 

Na maioria dos casos, a rede de interconexão será uma rede não gerenciada, uma conexão com a Internet. Uma opção disponível para abordar a QoS de ponta a ponta é o [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Recomendamos ainda implementar a QoS nas partes da rede sobre as quais você tem controle, ou seja, sua rede local. Assim, a qualidade das cargas de trabalho de comunicação em tempo real será melhor em toda a implantação, e os pontos de estrangulamento na implantação existente serão aliviados. 

## <a name="objectives"></a>Objetivos 

Este guia foca a maneira de priorizar o tráfego da comunicação em tempo real do Microsoft Teams, especialmente de voz e vídeo. Também é possível priorizar outros tipos de tráfego de acordo com as suas necessidades.

Há várias maneiras de priorizar o tráfego, mas a mais comum é usando marcações DSCP (Ponto de Código de Serviços Diferenciados). Elas podem ser aplicadas com base nos intervalos de portas, mas também via Objetos de Política de Grupo. Neste documento, vamos abordar os dois casos.

O controle da marcação DSCP via GPO (Objetos de Política de Grupo) garante que os computadores que ingressaram em um domínio recebam as configurações corretas e que essas configurações possam ser gerenciadas somente por um administrador. 

É importante entender que a QoS só funciona quando implementada em todos os links que conectam o autor e o destinatário da chamada. Se usarmos a QoS na rede interna e um usuário entrar de um local remoto, a priorização será possível somente dentro da rede interna gerenciada. Locais remotos poderiam receber uma conexão gerenciada por meio da implementação de uma VPN, mas não é recomendável executar o tráfego de comunicação em tempo real pela VPN.

> [!NOTE]
> Nossa recomendação é implementar um túnel dividido para usuários remotos conectados via VPN a fim de proporcionar a melhor experiência do usuário possível. Consulte o documento [Deploy-Guidance-VPN Split Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) para obter mais informações.

Em uma organização global com links gerenciados espalhados por vários continentes, é altamente recomendável usar a QoS, pois a largura de banda é limitada em comparação com a LAN (rede local).

## <a name="quality-of-service"></a>Qualidade de Serviço

Para oferecer um nível de serviço garantido para um aplicativo na rede, os dispositivos de rede subjacentes devem ser capazes de classificar diferentes tipos de tráfego. Um roteador, por exemplo, precisa diferenciar o tráfego de voz e o tráfego normal de navegação na Web, se for esperado que a voz receba um tratamento melhor. 

O DiffServ (Serviços Diferenciados) fornece uma estrutura na qual o tráfego é tratado por dispositivos de rede com prioridades baseadas no campo de ToS (tipo de serviços) no cabeçalho do pacote IPv4/IPv6. Os seis bits mais significativos do campo DiffServ são chamados de Ponto de Código de Serviços Diferenciados ou DSCP. Usando essa estrutura, é possível classificar o tráfego como um tipo de tráfego específico (voz) e marcá-lo (101110 ou 46, em decimal), de modo que, quando os dispositivos de rede processarem essas marcações, o tráfego poderá ser priorizado de maneira correspondente (neste exemplo, Expedited Forwarding).

Quando o tráfego de rede entra em um roteador, ele é colocado em uma fila. Se não houver QoS em vigor, haverá basicamente uma única fila, e os dados serão tratados por ordem de chegada. Isso quer dizer que o tráfego de voz (que é muito sensível a atrasos) poderia ficar travado atrás do tráfego de serviços de streaming online. Ao implementar a QoS, é possível definir várias filas com diferentes recursos de gerenciamento de congestionamento (como o Priority Queuing (PQ) e o Class Based Weighted Fair Queue (CBWFQ) da Cisco) e recursos para evitar congestionamentos (como o Weighted Random Early Detection (WRED)).

![Captura de tela de um diagrama que ilustra filas de QoS no Microsoft Teams.](media/Qos-in-Teams-Image2.png)

Figura 1: Visualização das filas de QoS

Quando essas peças estão no lugar, é possível fornecer uma qualidade de serviço previsível, pois a rede gerenciada subjacente sabe como classificar, marcar e priorizar o tráfego. Da perspectiva do Microsoft Teams, o item de configuração mais importante é a classificação e a marcação de pacotes. Mas é necessário um planejamento cuidadoso para alinhar a configuração do aplicativo com a configuração de rede subjacente para que a QoS de ponta a ponta seja bem-sucedida.

## <a name="qos-scenarios"></a>Cenários de QoS

Ao implementar a QoS para o Microsoft Teams, baseamos nossas orientações em quatro cenários iniciais:

1.  Você implantou ou está implantando o Microsoft Teams e planeja implementar a QoS via marcação baseada em porta. A marcação baseada em porta é o método mais confiável porque funciona universalmente em todas as plataformas e é o mais fácil de implementar. 

2.  Você implantou ou está implantando o Microsoft Teams e planeja implementar a QoS via marcação de Objetos de Política de Grupo. Às vezes, essa opção é usada em combinação com o cenário 1. Embora esse cenário seja inteiramente válido e esteja descrito a seguir, é importante saber que ele só funcionará para clientes Windows que ingressaram no domínio. Não é possível habilitar dispositivos que não são clientes Windows ingressados no domínio para a marcação de QoS\DSCP. 

3.  Você tem o Skype for Business Online implantado, incluindo a marcação de QoS, e está implantando o Microsoft Teams. Se for o seu caso, o Microsoft Teams respeitará a configuração existente e usará os mesmos intervalos de portas e a mesma marcação do cliente Skype for Business. Não deve ser necessária qualquer configuração adicional. 
    > [!NOTE]
    > Se você está usando a marcação de QoS de Nome do Aplicativo via Política de Grupo, deve adicionar “Teams.exe” como Nome do Aplicativo.
4.  Você implantou ou está implantando o Microsoft Teams e deseja implementar a QoS via marcação baseada em porta com um intervalo de portas personalizado.

## <a name="recommended-differentiated-services-code-point-dscp-markings"></a>Marcações DSCP (Ponto de Código de Serviços Diferenciados) recomendadas

O primeiro passo é classificar os fluxos de tráfego (por exemplo, de áudio e vídeo), utilizando os intervalos de portas exclusivos, não sobrepostos, com um valor de DSCP. O valor de DSCP atribuído aqui determinará a prioridade do tráfego que passa pela rede (com base na configuração de rede). Cada carga de trabalho recebe seu próprio valor de DSCP, embora alguns clientes possam definir o mesmo valor para voz e vídeo, atribuindo a elas a mesma prioridade na rede. 

O valor de DSCP que deve ser usado depende da maneira como a carga de trabalho é priorizada. Por exemplo, requisitos de negócios poderiam impor que o compartilhamento de aplicativos deve ser tratado com o mesmo nível de prioridade que o vídeo (e, portanto, marcado com o mesmo valor de DSCP que o vídeo). Outros ambientes podem ter uma estratégia de QoS existente já em vigor. 

A Tabela 1 abaixo mostra as marcações DSCP requeridas ao utilizar o Microsoft Teams com ExpressRoute. Isso serviria como um bom ponto de partida para clientes que não têm certeza sobre o que usar em seu próprio ambiente. Para saber mais, consulte [Requisitos de QoS para o ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


| Porta de origem do cliente|Protocolo|Categoria da mídia|Valor DSCP comum|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50.019|TCP/UDP|Áudio|46|Expedited Forwarding (EF)|
| 50.020 – 50.039|TCP/UDP|Vídeo|34|Assured Forwarding (AF41)|
| 50.040 – 50.059|TCP/UDP|Compartilhamento de aplicativos/área de trabalho e transferência de arquivos|18|Seletor de classe (CS3)|

Tabela 1: Marcações DSCP

Veja aqui algumas condições que devem ser observadas ao usar as informações da Tabela 1:

- O compartilhamento de arquivos e o compartilhamento de aplicativos usam o mesmo intervalo de portas de origem. Dessa maneira, usariam as mesmas marcações DSCP ao utilizar a marcação baseada em porta. Por isso, é necessário determinar qual prioridade se aplica melhor *às duas* modalidades (Interativa ou Padrão).
    
- Se houver planos de implementar o ExpressRoute no futuro e a QoS ainda não tiver sido implementada, é recomendável seguir as orientações fornecidas acima de modo que os valores de DSCP sejam iguais do remetente ao destinatário. 
    
## <a name="source-ports-used-by-teams"></a>Portas de origem usadas pelo Microsoft Teams

No Microsoft Teams, a QoS deve ser configurada com base nas portas de origem usadas pelas diferentes cargas de trabalho. Neste momento, não é possível configurar os intervalos de portas do lado do servidor, nem do lado do cliente. 

Para implantar a QoS, use os intervalos de portas de origem do cliente listados na Tabela 2 com as marcações DSCP de QoS associadas.

| Porta de origem do cliente|Protocolo|Categoria da mídia|Valor DSCP comum|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50.019|TCP/UDP|Áudio|46|Expedited Forwarding (EF)|
| 50.020 – 50.039|TCP/UDP|Vídeo|34|Assured Forwarding (AF41)|
| 50.040 – 50.059|TCP/UDP|Compartilhamento de aplicativos/área de trabalho e transferência de arquivos|18|Seletor de classe (CS3)|

Tabela 2: Intervalos de portas de origem do cliente

> [!NOTE]
> Se você já configurou a QoS com base nos intervalos de portas de origem para o Skype for Business Online, a mesma configuração se aplicará ao Microsoft Teams. Não é necessário alterar mais nada. Se você implantou o Skype for Business Server (no local), será necessário reestruturar suas Políticas de QoS.

## <a name="setting-differentiated-services-code-point-dscp-markings"></a>Definição de marcações DSCP (Ponto de Código de Serviços Diferenciados)

Há várias abordagens para definir as marcações DSCP corretas para a classificação do tráfego.

- Marcação DSCP no ponto de extremidade: em geral, essa é a opção preferencial, pois o próprio ponto de extremidade fornece as marcações corretas. No momento, isso deve ser feito usando um GPO, mas isso só é possível em clientes Windows que ingressaram no domínio. Os clientes Mac OSX ou móveis, por exemplo, não fornecem um mecanismo para marcar o tráfego com valores de DSCP.

- Baseada em portas usando ACLs nos roteadores: essa é uma opção muito comum em ambientes heterogêneos do Windows e do Mac. Nesse cenário, a equipe de rede marca o tráfego nos roteadores de entrada/saída (normalmente na WAN (rede de longa distância)) com base nos intervalos de portas de origem definidos para cada modalidade. Embora isso funcione em várias plataformas, a marcação é feita somente na borda da WAN, não por todo o caminho até o computador cliente, e agrega sobrecarga de gerenciamento.
    
- Combinação de marcações DSCP no cliente e ACLs baseadas em portas nos roteadores.
    
Se possível, recomendamos uma combinação das duas abordagens, usando um GPO para pegar a maioria dos clientes e também a marcação DSCP baseada em portas para garantir que clientes móveis, Mac e outros clientes possam receber um tratamento de QoS (parcial).

A definição do valor de DSCP para o intervalo de portas de origem predefinido no cliente Microsoft Teams pode ser feita usando a QoS baseada em política dentro da Política de Grupo. A tabela a seguir usa os intervalos de portas especificados para criar uma política para cada carga de trabalho.

| Tipo de tráfego do cliente|Início do intervalo de portas|Final do intervalo de portas|Valor de DSCP|
|---------|---------|---------|--------|
| Áudio|50000|50019|46|
| Vídeo|50020|50039|34|
| Compartilhamento de aplicativos|50040|50059|18|
| Transferência de arquivos|50040|50059|18|

Tabela 3: Intervalos de portas por tipo de tráfego

Observação: Não é possível mudar ou alterar os intervalos de portas definidos pelo Microsoft Teams. Consulte nesta página as informações mais recentes: https://support.microsoft.com/ kb/2409256

Depois que os intervalos de portas tiverem sido determinados, a próxima etapa é definir as configurações de QoS baseada em política dentro de um GPO (Objeto de Política de Grupo). Os detalhes desse procedimento estão disponíveis no [TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

As novas políticas que você criou só entrarão em vigor quando a Política de Grupo for atualizada nos computadores cliente. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

        gpudate.exe /force

Esse comando pode ser executado em qualquer janela de comando executada com credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.

## <a name="verifying-the-dscp-markings-in-gpo"></a>Verificação das marcações DSCP no GPO

Para verificar se os valores do GPO foram definidos, faça o seguinte:

1.  Use gpresult para verificar se as configurações do GPO foram recebidas pelo computador local. gpresult /R >gp.txt gerará um relatório e o enviará para um arquivo de texto, gp.txt.

    ![Captura de tela do Prompt de Comando do Administrador executando o comando gpresult.](media/Qos-in-Teams-Image3.png)

    Figura 2: Verificação dos Objetos de Política de Grupo aplicados
    > [!NOTE]
    > Como opção, você pode executar gpresult /H gp.html para produzir os mesmos dados em um relatório HTML mais amigável. 
2.  No arquivo gerado, procure o cabeçalho: Applied Group Policy Objects e verifique se os nomes dos GPOs criados estão na lista de políticas aplicadas. 

3.  Abra o editor do Registro e navegue até:

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Verifique os valores do Registro listados na Tabela 3 a seguir.
    
    | Nome | Tipo | Dados|
    |---------|---------|---------
    | Nome do Aplicativo|REG_SZ|Teams.exe|
    | Valor de DSCP|REG_SZ|46|
    | IP Local|REG_SZ|*|
    | Comprimento do Prefixo IP Local|REG_SZ|*|
    | Porta Local|REG_SZ|50000-50019|
    | Protocolo|REG_SZ|*|
    | IP Remoto|REG_SZ|*|
    | Prefixo do IP Remoto|REG_SZ|*|
    | Porta Remota|REG_SZ|*|
    | Taxa de Aceleração|REG_SZ|-1|
    
    Tabela 3: Valores do Registro do Windows para QoS

4.  Verifique se o Nome do Aplicativo está correto para o cliente que você está usando e se o valor de DSCP e a Porta Local refletem as configurações no GPO.

## <a name="validating-qos-analyzing-teams-traffic-on-the-network"></a>Validação da QoS: analisando o tráfego do Microsoft Teams na rede

O valor de DSCP definido pelo GPO precisa estar presente do autor da chamada até o destinatário da chamada para que a QoS seja efetiva. É possível verificar se o DSCP não foi alterado ou removido ao percorrer a rede examinando o tráfego gerado pelo cliente Microsoft Teams. 

Seria preferível capturar o tráfego no ponto de saída da rede. O espelhamento de porta pode ser usado em um comutador ou roteador para auxiliar na captura do tráfego na rede. 

### <a name="looking-at-network-traffic-using-network-monitor"></a>Exame do tráfego de rede usando o Monitor de Rede

A ferramenta Monitor de Rede pode ser baixada da Microsoft para analisar o tráfego de rede. Baixe o [Monitor de Rede 3.4](https://www.microsoft.com/download/4865).

Conecte o computador que está executando o Monitor de Rede à porta que foi configurada para o espelhamento de porta e inicie a captura de pacotes. Faça uma chamada usando o cliente Skype for Business. Verifique se a mídia foi estabelecida antes de desligar a chamada. Pare a captura, crie um filtro de exibição correspondente ao IP de origem do computador que fez a chamada e refine o filtro definindo o valor de DSCP 46 (hex 0xb8) como critério de pesquisa:

Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

![Captura de tela da caixa de diálogo Filtro de exibição no Monitor de Rede, mostrando os filtros que devem ser aplicados.](media/Qos-in-Teams-Image4.png)


Clique em **Aplicar** para ativar o filtro. Na janela **Frame Summary** (Resumo do Quadro), selecione o primeiro pacote UDP e examine os detalhes do quadro:

![Captura de tela da caixa de diálogo Frame Details (Detalhes do Quadro) no Monitor de Rede, destacando as configurações de DSCP.](media/Qos-in-Teams-Image5.png)

Expanda IPv4 e examine o valor no final da linha DSCP. Nesse exemplo, vemos que o valor de DSCP está definido como 46, que é o valor correto, já que a porta de origem usada é a 50019. Isso nos informa que a carga de trabalho é de voz. 

Repita a verificação para cada carga de trabalho que foi marcada pelo GPO. 

> [!NOTE]
> Confirme se as marcações também são respeitadas para o tráfego ponto a ponto. Isso pode ser feito instalando o Monitor de Rede em dois clientes e fazendo chamadas entre eles. Examine o tráfego de mídia que flui entre os clientes da maneira descrita acima.

### <a name="sample-filters-to-use-for-network-monitor-or-wireshark"></a>Filtros de exemplo para usar com o Monitor de Rede ou o Wireshark

|Uso  |Filtro de exemplo  |
|---------|---------|
|Voz (observação: a mixagem deve estar desligada)     |   udp.port==3479 AND Ipv4.DifferentiatedServicesField.DSCP==46      |
|Vídeo     | udp.port==3480 AND Ipv4.DifferentiatedServicesField.DSCP==34        |
|Compartilhamento de tela     |  udp.port==3481 AND Ipv4.DifferentiatedServicesField.DSCP==18       |

### <a name="filter-media-traffic-from-microsoft-relays-requires-azure-expressroutehttpsazuremicrosoftcomservicesexpressroute"></a>Filtro: tráfego de mídia de relés da Microsoft (requer o [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/))

ip.src em {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} e (udp.srcport em {3479 3480 3481} ou (udp.srcport ge 50000 e udp.srcport lt 60000))

### <a name="filter-media-traffic-to-microsoft-relays"></a>Filtro: tráfego de mídia de relés da Microsoft

ip.dst em {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} e (udp.dstport em {3479 3480 3481} ou (udp.dstport ge 50000 e udp.dstport lt 60000))


Você deve ver o tráfego de e para os relés da Microsoft. É possível verificar as marcações DSCP na camada IP no Wireshark conforme mostrado na próxima seção.

### <a name="expected-dscp-markings"></a>Marcações DSCP esperadas

Fluxos de áudio: 46

Fluxos de vídeo: 34

Fluxos de dados: 18

### <a name="filter-dscp-condition-to-network"></a>Filtro: condição de DSCP para rede

ip.dsfield.dscp em {46 34 18}



### <a name="looking-at-network-traffic-using-wireshark"></a>Exame do tráfego de rede usando o Wireshark

O Wireshark, https://www.wireshark.org/, é uma ferramenta eficiente que permite filtrar e gravar dados de rede para análise adicional. Conecte um computador que está executando o Wireshark à porta que foi configurada para o espelhamento de porta e inicie a captura de pacotes. Faça uma chamada usando o cliente Microsoft Teams. Verifique se a mídia foi estabelecida antes de desligar a chamada.

Pare o rastreamento de pacotes e crie um filtro para exibir apenas o IP de origem do computador em que o cliente Microsoft Teams está instalado. Por exemplo, *ip.src_host == 192.168.137.201* e procure os pacotes que usam uma porta de origem do intervalo especificado para voz, 50.000 – 50.019:

![Captura de tela do Wireshark com configurações de filtro.](media/Qos-in-Teams-Image6.png)
 

Marque o pacote e expanda o cabeçalho IPV4 no painel de detalhes do pacote:

![Captura de tela do Wireshark com as configurações de Differentiated Services Codepoint em destaque.](media/Qos-in-Teams-Image7.png)
 

Verifique se o valor de *Differentiated Services Codepoint* corresponde ao valor da carga de trabalho específica, nesse caso, 46 (binário 101110) para voz.

Repita a verificação para cada carga de trabalho que foi marcada pelo GPO.

> [!NOTE]
> Confirme se as marcações são respeitadas para o tráfego ponto a ponto. Isso pode ser feito instalando o WireShark ou o Monitor de Rede em dois clientes e fazendo chamadas entre eles. Examine o tráfego de mídia que flui entre os clientes da maneira descrita acima.

## <a name="summary"></a>Resumo

A Qualidade de Serviço é uma peça importante para fornecer experiências de nível empresarial com o Microsoft Teams. No entanto, é sempre importante lembrar que a QoS só é eficiente em redes gerenciadas corretamente. Dessa maneira, a equipe de implantação deve trabalhar de perto com as equipes de rede para garantir que as informações apropriadas sejam passadas em nível de rede, idealmente gerenciadas de ponta a ponta.

