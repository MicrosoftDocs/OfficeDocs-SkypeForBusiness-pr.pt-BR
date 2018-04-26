---
title: QoS em equipes da Microsoft - equipes da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 04/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Prepare a rede da sua organização para a Qualidade de Serviço (QoS) no Microsoft Teams
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 884055dce490b9db8fd31f6e52042a4315633e00
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a>Qualidade de Serviço (QoS) no Microsoft Teams

Este artigo ajudará você a preparar a rede da sua organização Quality of a Service (QoS) no Microsoft Teams.
QoS é um mecanismo que você usará para priorizar certos tipos de tráfego de rede. Priorizar o tráfego de serviços de comunicação em tempo real, como equipes é importante para proporcionar uma experiência de usuário de nível de negócios. Para QoS seja realmente eficaz, você deve configurar uma conexão com capacidade para QoS da extremidade final (PC, comutadores de rede e roteadores para a nuvem), pois qualquer parte do caminho que está falhando para dar suporte a QoS pode prejudicar a qualidade da chamada inteira.

![a relação entre redes de uma organização e serviços do Office 365: conectam a rede e os dispositivos com uma rede de interconexão, que por sua vez, se conecta com os serviços do Office 365 nuvem voz e conferência de áudio no local.] (media/Qos-in-Teams-Image1.png "a relação entre redes de uma organização e serviços do Office 365: conectam a rede e os dispositivos com uma rede de interconexão, que por sua vez, se conecta com os serviços do Office 365 nuvem voz e conferência de áudio no local.")

_Figura 1. A relação entre redes de uma organização e serviços do Office 365_
 

Na maioria dos casos, a rede de interconexão será uma conexão de internet de rede não gerenciado. Uma opção disponível para QoS de ponta a ponta de endereços é [ExpressRoute do Windows Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Ainda recomendamos que você implemente QoS nas partes da rede você tenha controle sobre, notadamente sua rede local. Isso irá aumentar a qualidade das cargas de trabalho de comunicação em tempo real em toda sua implantação e atenuar os pontos de estrangulamento na implantação existente. 


## <a name="prioritize-teams-network-traffic-for-qos"></a>Priorizar o tráfego de rede de equipes para QoS 

Este artigo aborda como priorizar o tráfego de comunicação em tempo real de equipes — ou seja, voz e vídeo. Você também pode priorizar os outros tipos de tráfego, com base em suas necessidades.

Há várias maneiras de priorizar o tráfego, mas a mais comum é usando marcações DSCP (Ponto de Código de Serviços Diferenciados). Eles podem ser aplicados ("marcados") com base em intervalos de porta e também por meio de objetos de diretiva de grupo. Abordaremos ambos neste artigo. Recomendamos que você use marcação com base em intervalos de porta, pois ele funcionará para todos os dispositivos, e não apenas aquelas que ingressou no domínio.

Controlando a marcação de DSCP por meio de objetos de diretiva de grupo garante que os computadores de domínio recebam as configurações corretas e que somente um administrador pode gerenciá-los.
 
É importante entender que QoS funciona apenas quando implementada em todos os links que conectar o chamador para o receptor. Se você usar a QoS na rede interna e um usuário entrar em um local remoto, você pode priorizar somente dentro de sua rede interna, gerenciada. Embora os locais remotos podem receber uma conexão gerenciada por meio da implementação de uma rede virtual privada (VPN), é recomendável que você evite executando o tráfego de comunicação em tempo real através da VPN.

> [!NOTE]
> É recomendável que você implemente túnel em divisão para usuários remotos conectados VPN maximizar a qualidade da experiência do usuário. Faça o download do documento [Orientação-Deploy-VPN divisão túnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) MyAdvisor para obter mais informações.

Em uma organização global com links gerenciadas que abrangem continentes, QoS é altamente recomendável porque a largura de banda para esses links é limitada em comparação com o da LAN.

## <a name="qos-queues"></a>Filas de QoS

Para fornecer um nível de serviço para um aplicativo garantido na rede, os dispositivos de rede subjacente devem ter uma maneira de classificar os diferentes tipos de tráfego. Se sua organização quiser priorizam do tráfego de voz sobre outro tráfego, um roteador (por exemplo) deve ser capaz de distinguir entre o tráfego de voz e o tráfego normal de navegação da web. 

Serviços diferenciados (DiffServ) oferece uma estrutura na qual o tráfego será priorizado diferentes por dispositivos de rede com base no tipo de campo de serviços (ToS) no cabeçalho de um pacote IPv4/IPv6. Os seis bits mais significativos do campo DiffServ são o ponto de código de serviços diferenciados ou DSCP. Usando essa estrutura, tráfego pode ser classificado como um tipo específico de tráfego (por exemplo, voz) e, em seguida, marcado (101110 ou 46 em decimal para tráfego de voz), para que quando os dispositivos de rede processam essas marcas, o tráfego pode ser priorizados adequadamente ( Encaminhamento expedido, neste exemplo).

Quando o tráfego de rede entra em um roteador, o tráfego é colocado em uma fila — se não houver nenhuma QoS in-loco, essencialmente, há apenas uma fila e os dados são tratados como first-in, First. Isso significa que o tráfego de voz (que é muito sensível a atrasos) pode cair por trás de tráfego do online services streaming. Ao implementar o QoS, você pode definir várias filas usando os recursos de gerenciamento de congestionamento diferentes (por exemplo, da Cisco enfileiramento prioritário e baseada em classe ponderada justa fila [CBWFQ]) e recursos de prevenção de congestionamento (por exemplo, aleatória ponderada antecipada [de detecção WRED]).

![Largura de banda total disponível é dividida entre várias filas — áudio, vídeo e outros tráfegos — que tiverem sido atribuídas prioridades diferentes.] (media/Qos-in-Teams-Image2.png "Largura de banda total disponível é dividida entre várias filas — áudio, vídeo e outros tráfegos — que tiverem sido atribuídas prioridades diferentes.")

_Figura 2. Filas de QoS visualizadas_

Depois que essas partes estão funcionando, é possível entregar QoS previsível porque a rede gerenciada subjacente agora entende como classificar, marcar e priorizar o tráfego. Sob a perspectiva de equipes, a etapa de configuração mais importante é a classificação e a marcação dos pacotes, mas para QoS de ponta a ponta obter êxito, você também precisará Alinhe cuidadosamente a configuração do aplicativo com a configuração de rede subjacente.

## <a name="teams-qos-scenarios"></a>Cenários de QoS de equipes

As orientações para a implementação de QoS para equipes se baseia em quatro cenários:

*  **Cenário 1:** Você tiver implantado, ou estiver implantando, equipes e estiver planejando a implementação da QoS via baseados na porta marcação. A marcação baseados na porta é o método mais confiável, porque ele funciona universal em toda a todas as plataformas e é o mais fácil para implementar.  

*  **Cenário 2:** Você tiver implantado, ou estiver implantando, equipes e estiver planejando implementar QoS via marcação de objeto de diretiva de grupo. Às vezes, essa opção é usada em combinação com o cenário 1. Embora esta situação é válida inteiramente, é importante entender só funcionará para clientes do domínio Windows. Qualquer dispositivo que não é um cliente do domínio do Windows não será ativado para DSCP marcação.

*  **Cenário 3:** Você tiver implantado o Skype para negócios Online, incluindo a marcação de QoS e agora está implantando equipes. Se for o seu caso, o Microsoft Teams respeitará a configuração existente e usará os mesmos intervalos de portas e a mesma marcação do cliente Skype for Business. Na maioria dos casos, nenhuma configuração adicional será necessária. 
 
    > [!NOTE]
    > Se você estiver usando a QoS de nome de aplicativo marcação via diretiva de grupo, você deve adicionar Teams.exe como o nome do aplicativo.

*  **Cenário 4:** Você tiver implantado, ou estiver implantando, equipes e quiser implementar o QoS via baseados na porta marcação usando um intervalo de porta personalizados.

## <a name="recommended-dscp-markings"></a>Marcações de DSCP recomendadas

A primeira etapa é classificar os fluxos de tráfego (por exemplo, áudio e vídeo), atribuindo valores DSCP para os intervalos de porta exclusivo e não sobrepostos. O valor DSCP atribuído aqui determinará a prioridade do tráfego passar pela rede, com base na configuração de rede. Cada carga de trabalho obtém seu próprio valor DSCP, porém não necessariamente um valor exclusivo — alguns clientes podem definir o mesmo valor para cargas de trabalho de voz e vídeo, concedendo a eles a mesma prioridade na rede.  

O valor DSCP a ser usado depende de como você deseja priorizar a carga de trabalho. Por exemplo, requisitos de negócios podem exigir que você forneça o aplicativo a mesma prioridade de vídeo de compartilhamento (e, portanto, marcá-lo com o mesmo valor DSCP de vídeo). Outros ambientes podem ter uma estratégia de QoS existente no lugar, que ajudará você a determinar a prioridade das cargas de trabalho de rede. 

A tabela 1 mostra as marcas de DSCP necessárias ao utilizar as equipes com ExpressRoute. Essas marcas podem servir como um bom ponto de partida para os clientes que não tem certeza sobre o que usar em seus próprios ambientes. Para saber mais, consulte [Requisitos de QoS para o ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


_Tabela 1. Marcações de DSCP_
    
| Intervalo de porta de origem do cliente |Protocolo|Categoria da mídia|Valor de DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Áudio|46|Expedited Forwarding (EF)|
| 50,020 – 50,039|TCP/UDP|Vídeo|34|Assured Forwarding (AF41)|
| 50,040 – 50,059|TCP/UDP|Compartilhamento de aplicativo/área de trabalho|18|Assured Forwarding (AF21)|

Veja aqui algumas condições que devem ser observadas ao usar as informações da Tabela 1:
    
-  Se você pretende implementar ExpressRoute no futuro e ainda não foi implementado QoS, recomendamos que você siga as orientações na tabela 1, para que os valores DSCP são os mesmos do remetente para o receptor. 

-  Todos os clientes, incluindo clientes móveis e dispositivos de equipes, usarão esses intervalos de porta e serão afetados pela implementar qualquer política DSCP que usa esses intervalos de porta de origem. Os únicos clientes que continuarão a usar portas dinâmicas são os clientes baseados em navegador (ou seja, os clientes que permitem que os participantes participar de reuniões usando seus navegadores).

-  Embora o cliente Mac usem os mesmos intervalos de porta, o cliente Mac também usa valores codificados para (EF) de áudio e vídeo (AF41). Esses valores não são configuráveis.
 
    
## <a name="source-ports-used-by-teams"></a>Portas de origem usadas pelo Microsoft Teams

No Microsoft Teams, a QoS deve ser configurada com base nas portas de origem usadas pelas diferentes cargas de trabalho. Nenhum dos intervalos de porta do servidor nem do cliente são configuráveis no momento. 

Observe os intervalos de porta de origem do cliente listados na tabela 2 e usar suas marcações de QoS DSCP associadas.

_Tabela 2. Intervalos de porta de origem do cliente_

| Intervalo de porta de origem do cliente |Protocolo|Categoria da mídia|Valor de DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Áudio|46|Expedited Forwarding (EF)|
| 50,020 – 50,039|TCP/UDP|Vídeo|34|Assured Forwarding (AF41)|
| 50,040 – 50,059|TCP/UDP|Compartilhamento de aplicativo/área de trabalho|18|Assured Forwarding (AF21)|

O método recomendado de implementação essas políticas de QoS é usar as portas de origem do cliente com um endereço IP de origem e destino de "Nenhum". Isso irá capturar ambas tráfego de mídia de entrada e saída na rede interna. 

> [!NOTE]
> Se você já tiver configurado a QoS com base em intervalos de porta de origem para Skype para Business Online, a mesma configuração será aplicada às equipes e nenhuma alteração será necessária. Se você implantou Skype para Business Server local, você precisará reconstruir suas políticas de QoS.

## <a name="setting-dscp-markings"></a>Definindo as marcações de DSCP

Há várias abordagens para definir as marcas de DSCP apropriadas para a classificação de tráfego:

-  **a marcação DSCP no ponto de extremidade:** Isso geralmente é a opção preferencial, porque o ponto de extremidade próprio fornece as marcações adequadas. No momento isso pode ser feito usando-se um objeto de diretiva de grupo, mas só pode ser usado em clientes do domínio Windows. Clientes móveis não fornecem um mecanismo para marcar o tráfego usando valores DSCP. Embora você não pode definir não&ndash;clientes associados a um domínio do Windows ao tráfego de marca, clientes como o Mac OS ter codificadas marcas e sempre será marcar tráfego conforme descrito acima.

-  **Usando listas de controle de acesso (ACLs) em roteadores de marcação de DSCP baseados na porta:** Essa é uma opção muito comuns encontrada em ambientes Windows e Mac heterogêneos. Neste cenário, a equipe de rede marca o tráfego nos roteadores de entrada/saída (normalmente localizado na rede de longa distância) com base nos intervalos de porta de origem definidos para cada modalidade. Embora isso funcione em todas as plataformas, ele marca somente o tráfego da borda de WAN — não totalmente para a máquina cliente — e, portanto, gera sobrecarga de gerenciamento.
    
-  **Uma combinação de marcações de DSCP no ponto de extremidade e baseados na porta ACLs em roteadores:** Recomendamos esta combinação, se possível em seu ambiente. Use um objeto de diretiva de grupo para capturar a maioria dos clientes e também utilizar para garantir que mobile, Mac e outros clientes ainda obterão tratamento de QoS (pelo menos parcialmente) de marcação de DSCP baseados na porta.
    
Você pode usar a QoS baseada em diretivas dentro da diretiva de grupo para definir o valor DSCP para o intervalo de porta de origem predefinidos no cliente equipes. Use os intervalos de porta especificados na tabela 3 para criar uma política para cada carga de trabalho.

_Tabela 3. Intervalos de porta por tipo de tráfego_
| Tipo de tráfego do cliente|Início do intervalo de portas|Final do intervalo de portas|Valor de DSCP|
|---------|---------|---------|--------|
| Áudio|50000|50019|46|
| Vídeo|50020|50039|34|
| Compartilhamento de aplicativos|50040|50059|18|

> [!NOTE]
> Os intervalos de porta definidos por equipes não podem ser alterados. Examine [Este artigo de suporte](https://support.microsoft.com/kb/2409256) para obter as informações mais recentes. 

Depois que você identificou os intervalos de porta, a próxima etapa é definir as configurações de QoS baseada em diretivas dentro de um objeto de diretiva de grupo. Para obter mais informações sobre essas etapas podem ser encontradas no [artigo da TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada em seus computadores cliente. Embora a diretiva de grupo for atualizada periodicamente por si só, você pode forçar uma atualização imediata.

### <a name="force-group-policy-refresh"></a>Atualização de diretiva de grupo Force

1. Em cada computador para o qual você deseja atualizar a diretiva de grupo, abra um console de comando. Certifique-se de que o console de comando está definido para executar como administrador.

2. No prompt de comando, digite:
```
    gpudate.exe /force
```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verifique se as marcações de DSCP no objeto de diretiva de grupo

Para verificar se os valores do objeto de diretiva de grupo foram definidos, execute as seguintes etapas.

1.  Abra um console de comando. Certifique-se de que o console de comando está definido para executar como administrador.

2.  No prompt de comando, digite: 
    ```
    gpresult /R >gp.txt
    ```

    Isso irá gerar um relatório e enviá-la para um arquivo de texto chamado GP. txt. Como alternativa, você pode inserir o seguinte comando para produzir os mesmos dados em um relatório HTML mais legível chamado gp.html:
    ```
    gpresult /H >gp.html
    ```
 
   ![Captura de tela da janela do console, executando o comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de tela da janela do console, executando o comando gpresult.")

3.  No arquivo gerado, procure por título de **Objetos de diretiva de grupo aplicados** e verifique se os nomes dos objetos de diretiva de grupo criados anteriormente estão na lista de diretivas aplicadas. 

4.  Abra o Editor do registro e vá para:

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Verifique se os valores para as entradas do Registro listadas na tabela 3.

    _Tabela 3. Valores para entradas de registro do Windows para QoS_
    
    | Nome | Tipo | Dados|
    |---------|---------|---------
    | Nome do Aplicativo|REG_SZ|Teams.exe|
    | Valor de DSCP|REG_SZ|46|
    | IP Local|REG_SZ|*|
    | Comprimento do Prefixo IP Local|REG_SZ|*|
    | Porta Local|REG_SZ|50000-50019|
    | Protocolo|REG_SZ|*|
    | IP Remoto|REG_SZ|*|
    | Prefixo IP remoto|REG_SZ|*|
    | Porta Remota|REG_SZ|*|
    | Taxa de Aceleração|REG_SZ|-1|
    
5.  Verificar se o valor para a entrada de nome do aplicativo está correto para o cliente que você está usando e verificar que o valor DSCP e a porta Local entradas reflitam as configurações no objeto de diretiva de grupo.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Validar a QoS ao analisar o tráfego de equipes na rede

O valor DSCP definido pelas necessidades de objeto de diretiva de grupo estar presentes do chamador para o receptor na ordem de QoS para serem eficientes. Examinando o tráfego gerado pelo cliente equipes, você pode verificar que o valor DSCP não será alterado ou retirado quando o tráfego de carga de trabalho de equipes percorre a rede. 

De preferência, você capturar o tráfego no ponto de saída de rede. Você pode usar o espelhamento de porta em um comutador ou roteador para ajudá-lo com isso.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Use o Monitor de rede para verificar os valores DSCP

Monitor de rede é uma ferramenta que você pode [fazer o download da Microsoft](https://www.microsoft.com/download/4865) para analisar o tráfego de rede.

1.  No PC executando o Monitor de rede, conecte-se à porta que foi configurada para o espelhamento de porta e iniciar a captura de pacotes. 

2.  Fazer uma chamada usando o Skype para o cliente de negócios. Certifique-se de mídia foi estabelecida antes de desligar a chamada. 

3.  Pare a captura.

4. No campo de **Filtro de exibição** , use o endereço IP de origem do PC que fez a chamada e refinar o filtro definindo o valor DSCP 46 (hex 0xb8) como critérios de pesquisa, conforme mostrado no exemplo a seguir:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Captura de tela da caixa de diálogo de filtro de exibição no Monitor de rede, mostrando os filtros a serem aplicados.] (media/Qos-in-Teams-Image4.png "Captura de tela da caixa de diálogo de filtro de exibição no Monitor de rede, mostrando os filtros a serem aplicados.")

5.  Selecione **Aplicar** para ativar o filtro.

6.  Na janela de **Quadro de resumo** , selecione o primeiro pacote UDP.

7.  Na janela **Detalhes do quadro** , expanda o item de lista de IPv4 e observe o valor no final da linha que começa com **DSCP**. 

    ![Captura de tela da caixa de diálogo Detalhes do quadro no Monitor de rede, as configurações de DSCP de realce.] (media/Qos-in-Teams-Image5.png "Captura de tela da caixa de diálogo Detalhes do quadro no Monitor de rede, as configurações de DSCP de realce.")

Neste exemplo, o valor DSCP é definido como 46. Isso está correto, porque a porta de origem usada é 50019, que indica que isso é uma carga de trabalho de voz. 

Repita a verificação para cada carga de trabalho que foi marcada pelo GPO. 
