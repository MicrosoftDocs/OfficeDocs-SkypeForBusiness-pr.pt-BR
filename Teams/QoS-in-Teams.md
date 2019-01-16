---
title: Implementar a qualidade de serviço em equipes da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Prepare a rede da sua organização para a Qualidade de Serviço (QoS) no Microsoft Teams
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: b519327b37c61a126c5101080f0c1eee9f8582f5
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "28326728"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar a qualidade do serviço (QoS) em equipes da Microsoft

Este artigo ajudará você a preparar a rede da sua organização Quality of a Service (QoS) no Microsoft Teams.

Você pode usar a QoS para priorizar o tráfego de rede que é sensível para atrasos de rede sobre tráfego menos confidencial. Uma simples analogia é que a QoS cria virtual "pistas expressa, mas" em seus dados nunca tão alguns tipos de dados de rede ou raramente encontrar atrasos.
Ao priorizar o tráfego de comunicação em tempo real, como chamadas ou reuniões compartilhadas em equipes que você pode mais confiável fornecem uma experiência de usuário de nível de negócios. Sem algum tipo de QoS, talvez você veja os seguintes problemas de qualidade de voz e vídeo:

- Tremulação – pacotes de mídia que chegam em taxas diferentes.
- Perda de pacote – pacotes descartados, que pode resultar em palavras ou sílabas faltando.
- Tempo de atraso de ida e volta (tempo de resposta) – demorando muito para alcançar seus destinos de pacotes de mídia.

Para QoS seja realmente eficaz, as configurações de QoS consistentes devem ser aplicadas de ponta a ponta em sua organização (usuário PCs, comutadores de rede e roteadores para a nuvem), pois qualquer parte do caminho que está falhando para dar suporte a suas prioridades de QoS pode prejudicar a qualidade das chamadas , vídeo e compartilhamento de tela.

QoS é um mecanismo que você pode usar para priorizar certos tipos de tráfego de rede que são sensíveis a atrasos de rede sobre outro tráfego que são menos confidencial. Uma simples analogia é que a QoS cria virtual "pistas expressa, mas" em seus dados de rede, portanto alguns tipos de dados nunca ou raramente encontrar atrasos.

Ao priorizar o tráfego de comunicação em tempo real, como chamadas ou reuniões compartilhadas em equipes que você pode mais confiável fornecem uma experiência de usuário de nível de negócios. Quando você não implementa QoS, telas compartilhadas em reuniões podem congelar, vídeo pode pixellate e mudança de cor e chamadas de voz podem se tornar entrecortado e difíceis ou impossíveis de entender. Para QoS seja realmente eficaz, as configurações de QoS consistentes devem ser aplicadas de ponta a ponta em sua organização (usuário PCs, comutadores de rede e roteadores para a nuvem), pois qualquer parte do caminho que está falhando para dar suporte a suas prioridades de QoS pode prejudicar a qualidade das chamadas , vídeo e compartilhamento de tela.

![A relação entre redes de uma organização e serviços do Office 365: conectam a rede e os dispositivos com uma rede de interconexão, que por sua vez, se conecta com os serviços do Office 365 nuvem voz e conferência de áudio no local.](media/Qos-in-Teams-Image1.png) 

Uma opção disponível para QoS de ponta a ponta de endereços é [ExpressRoute do Windows Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Ainda assim, é recomendável que você implemente o QoS em sua rede local. Isso irá aumentar a qualidade das cargas de trabalho de comunicação em tempo real em toda sua implantação e atenuar os pontos de estrangulamento. 

Na maioria dos casos, a rede de sua empresa conectar-se para a nuvem será uma conexão de internet de rede não gerenciado onde você não poderá definir confiável QoS. Uma opção disponível para permitir a QoS de ponta a ponta realmente é [ExpressRoute do Windows Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Ainda recomendamos que você implemente QoS nas partes da rede de ponta a ponta você tenha controle sobre, notadamente sua rede local. Isso irá aumentar a qualidade das cargas de trabalho de comunicação em tempo real em toda sua implantação e atenuar os pontos de estrangulamento na implantação existente.

## <a name="prioritize-teams-network-traffic-for-qos"></a>Priorizar o tráfego de rede de equipes para QoS 

Este artigo aborda como priorizar o tráfego de comunicação em tempo real de equipes — ou seja, voz e vídeo. Você também pode priorizar os outros tipos de tráfego, com base em suas necessidades.

Há várias maneiras para priorizar o tráfego, mas o mais comum é usando as marcas (DSCP) ponto de código de serviços diferenciados. Eles podem ser aplicados ("marcados") com base em intervalos de porta ou por meio de objetos de diretiva de grupo. Abordaremos ambos neste artigo. Recomendamos que você use marcação com base em intervalos de porta, pois ele funcionará para todos os dispositivos, e não apenas aquelas que ingressou no domínio.

Controlando a marcação de DSCP por meio de objetos de diretiva de grupo garante que os computadores de domínio recebam as configurações corretas e que somente um administrador pode gerenciá-los.

É importante entender que QoS funciona apenas quando implementada em todos os links que conectar o chamador para outro. Se você usar a QoS na rede interna e um usuário entrar em um local remoto, você pode priorizar somente dentro de sua rede interna, gerenciada. Embora os locais remotos podem receber uma conexão gerenciada por meio da implementação de uma rede virtual privada (VPN), é recomendável que você evite executando o tráfego de comunicação em tempo real através da VPN.

> [!NOTE]
> É recomendável que você implemente túnel em divisão para usuários remotos conectados VPN maximizar a qualidade da experiência do usuário. Faça o download do documento [Orientação-Deploy-VPN divisão túnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) MyAdvisor para obter mais informações.

Em uma organização global com links gerenciadas que abrangem continentes, é altamente recomendável QoS porque a largura de banda para esses links é limitada em comparação com o da LAN.

## <a name="qos-queues"></a>Filas de QoS

Para fornecer a QoS, os dispositivos de rede devem ter uma maneira de classificação de tráfego e devem ser capazes de distinguir voz ou vídeo de outros tráfego de rede. 

Serviços diferenciados (DiffServ) usa o tipo de campo de serviços (ToS) no cabeçalho de um pacote IPv4/IPv6 para definir a prioridade para dispositivos de rede. Os seis bits mais significativos do campo DiffServ são o ponto de código de serviços diferenciados ou DSCP. Com isso, o tráfego pode ser classificado como um tipo específico (por exemplo, voz) e, em seguida, marcado (101110 ou 46 em decimal para tráfego de voz), para que quando os dispositivos de rede processam essas marcas, o tráfego pode ser priorizado adequadamente (expedited encaminhamento, em Neste exemplo).

Quando o tráfego de rede entra em um roteador, o tráfego é colocado em uma fila. Se não houver nenhuma QoS in-loco, há apenas uma fila e os dados são tratados como first-in, First. Isso significa que o tráfego de voz (que é muito sensível a atrasos) pode cair por trás de tráfego do online services streaming. Quando você implementa a QoS, você pode definir várias filas usando os recursos de gerenciamento de congestionamento diferentes (por exemplo, da Cisco enfileiramento prioritário e baseada em classe ponderada justa fila [CBWFQ]) e recursos de prevenção de congestionamento (por exemplo, aleatória ponderada antecipada [de detecção WRED]).

![Largura de banda total disponível é dividida entre várias filas — áudio, vídeo e outros tráfegos — que tiverem sido atribuídas prioridades diferentes.] (media/Qos-in-Teams-Image2.png "Largura de banda total disponível é dividida entre várias filas — áudio, vídeo e outros tráfegos — que tiverem sido atribuídas prioridades diferentes.")

_Figura 2. Exemplos de filas de QoS_

Depois que essas partes estão funcionando, é possível entregar QoS previsível porque a rede agora entende como classificar, marcar e priorizar o tráfego. Sob a perspectiva de equipes, a etapa de configuração mais importante é a classificação e a marcação dos pacotes, mas para QoS de ponta a ponta obter êxito, você também precisará Alinhe cuidadosamente a configuração do aplicativo com a configuração de rede subjacente.

## <a name="teams-qos-scenarios"></a>Cenários de QoS de equipes

As orientações para a implementação de QoS para equipes se baseia em quatro cenários:

*  **Cenário 1:** Você tiver implantado ou estiver implantando equipes e pretende implementar QoS via baseados na porta marcação. A marcação baseados na porta é o método mais confiável, pois universal funciona em todas as plataformas e é o mais fácil para implementar.  

*  **Cenário 2:** Você tiver implantado ou estiver implantando equipes e planeja a implementação de QoS via marcação de objeto de diretiva de grupo. Às vezes, essa opção é usada em combinação com o cenário 1. Embora esta situação é totalmente válida, ele só funcionará para clientes associados a um domínio do Windows. Qualquer dispositivo que não é um cliente do domínio do Windows não será ativado para DSCP marcação.

*  **Cenário 3:** Você tiver implantado o Skype para negócios Online, incluindo a marcação de QoS e agora está implantando equipes. Se for o seu caso, o Microsoft Teams respeitará a configuração existente e usará os mesmos intervalos de portas e a mesma marcação do cliente Skype for Business. Na maioria dos casos, nenhuma configuração adicional será necessária. 

    > [!NOTE]
    > Se você estiver usando a QoS de nome de aplicativo marcação via diretiva de grupo, você deve adicionar Teams.exe como o nome do aplicativo.

*  **Cenário 4:** Você tiver implantado ou estiver implantando equipes e quiser implementar o QoS via baseados na porta marcação usando um intervalo de porta personalizados.

## <a name="implement-qos"></a>Implementar o QoS

Em um nível muito alto, a implementação da QoS exige estas etapas:

1. Determine os requisitos de largura de banda e de rota.

2. Use as marcações de DSCP e intervalos de portas para classificar o tráfego.

3. Defina as configurações de QoS baseada em diretivas dentro de um objeto de diretiva de grupo.

4. Verifique se os intervalos de porta no objeto de diretiva de grupo.

5. Valide o QoS ao analisar o tráfego de equipes na rede.

Como se preparar para implementar o QoS, lembre-se as seguintes diretrizes:

- O caminho mais curto para o Office 365 é melhor.

- Fechando portas apenas levará a degradação da qualidade.

- Qualquer obstáculos intermediária, como proxies, não são recomendados.

- Limite o número de saltos de:

    - Cliente para a borda da rede – saltos de 3 a 5.
    - ISP para a borda da rede Microsoft – 3 saltos
    - Borda da rede Microsoft ao destino final – irrelevante 

Para obter informações sobre como configurar portas de firewall, vá para o [Office 365 URLs e intervalos IP](office-365-urls-ip-address-ranges.md).

## <a name="determine-bandwidth-requirements"></a>Determinar os requisitos de largura de banda

Antes de configurar QoS for Microsoft Teams, é importante preparar sua rede for Microsoft Teams e determinar os requisitos de largura de banda. Fornecimento de QoS em sua rede exige a reserva de um volume definido de largura de banda em cada link para tráfego em tempo real. (Se a largura de banda que não é necessária para o tráfego em tempo real a qualquer momento, ele pode ser usado para outro tráfego.)

Congestionamento de tráfego em uma rede muito afetará a qualidade da mídia. Falta de líderes de largura de banda a diminuição do desempenho e uma experiência de usuário ruim, portanto, considere como ponto de partida para implantação de equipes de planejamento de largura de banda. À medida que cresce de uso e a adoção de equipes, uso de relatórios para fazer ajustes necessários. 

Planejador de rede disponível em FastTrack é útil quando você estiver determinando os requisitos de largura de banda.

### <a name="requirements-for-a-connection-from-your-network-to-microsoft-network-edge"></a>Requisitos para uma conexão de rede para a borda da rede Microsoft

Para obter a melhor qualidade de mídia, as metas de desempenho de rede ou limites mostrados na tabela 1 são necessários para uma conexão de rede da sua organização e o limite de rede da Microsoft.

> [!IMPORTANT]
> Conectividade entre um cliente de equipes em sua rede de empresa para serviços do Office 365 deve atender aos seguintes requisitos de desempenho de rede.

_Tabela 1. Métricas de desempenho de rede - cliente aos serviços do Office 365_

| Métrica | Destino  |
|--------|--------|
| Latência (unidirecional) | < 50 milissegundos |
| Latência (tempo ida e volta (tempo de resposta) | < 100 milissegundos |
| Perda de pacote de intermitência | < 10% durante qualquer intervalo de 200 milissegundos |
| Perda de pacotes | < 1% durante qualquer intervalo segundo 15 |
| Tremulação de entre chegada de pacotes | < 30 milissegundos durante qualquer intervalo segundo 15 |
| Novo pedido de pacotes | % de 0,05 < sem pacotes de ordem |

O destino de métricas de latência supõe que o site da empresa ou sites e as bordas da Microsoft estão em continente o mesmo.

O site da sua empresa para a conexão de borda de rede Microsoft inclui primeiro salto acesso à rede, que pode ser WiFi ou outra tecnologia sem fio.

A meta de desempenho de rede considera a largura de banda adequada e/ou o planejamento de QoS. Em outras palavras, os requisitos se aplicam diretamente para o tráfego de mídia em tempo real de equipes quando a conexão de rede está sob uma carga de pico.

### <a name="requirements-for-a-connection-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos para uma conexão de sua borda da rede para a Microsoft de borda de rede

Tabela 2 mostra as metas de desempenho de rede ou limites necessários para a conexão entre a borda da rede e a borda da rede Microsoft. Isso exclui a rede interna da sua organização ou WAN e serve como um guia ao testar o tráfego de rede que será enviado pela internet ou por meio de uma rede de parceiros ExpressRoute.

> [!IMPORTANT]
> Conectividade entre a borda da rede da sua empresa às bordas rede Microsoft deve atender aos seguintes requisitos de desempenho de rede.

_Tabela 2. Métricas de desempenho de rede - de uma borda_

| Métrica | Destino  |
|--------|--------|
| Latência (unidirecional) | < 30 milissegundos |
| Latência (tempo ida e volta (tempo de resposta) | < 60 milissegundos |
| Perda de pacote de intermitência | < 1% durante qualquer intervalo de 200 milissegundos |
| Perda de pacotes | < 0,1% durante qualquer intervalo segundo 15 |
| Tremulação de entre chegada de pacotes | < 15 milissegundos durante qualquer intervalo segundo 15 |
| Novo pedido de pacotes | < 0,01% sem pacotes de ordem |


## <a name="recommended-dscp-markings"></a>Marcações de DSCP recomendadas

Quando você estiver pronto para configurar a QoS, sua primeira etapa é classificar os fluxos de tráfego (por exemplo, áudio e vídeo), atribuindo valores DSCP para os intervalos de porta exclusivo e não sobrepostos. O valor DSCP atribuído aqui determinará a prioridade do tráfego passar pela rede, com base na configuração de rede. Cada carga de trabalho obtém seu próprio valor DSCP, porém não necessariamente um valor exclusivo — talvez você queira definir o mesmo valor para cargas de trabalho de voz e vídeo, concedendo a eles a mesma prioridade na rede.  

O valor DSCP a ser usado depende de como você deseja priorizar a carga de trabalho. Por exemplo, requisitos de negócios podem exigir que você forneça o aplicativo a mesma prioridade de vídeo de compartilhamento (e, portanto, marcá-lo com o mesmo valor DSCP de vídeo). Outros ambientes podem ter uma estratégia de QoS existente no lugar, que ajudará você a determinar a prioridade das cargas de trabalho de rede. 

A tabela 3 mostra as marcas de DSCP necessárias para as equipes com ExpressRoute. Essas marcas podem servir como um bom ponto de partida para os clientes que não tem certeza sobre o que usar em seus próprios ambientes. Para saber mais, consulte [Requisitos de QoS para o ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Tabela 3. Marcações de DSCP_

| Intervalo de porta de origem do cliente |Protocolo|Categoria da mídia|Valor de DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Áudio|46|Expedited Forwarding (EF)|
| 50,020 – 50,039|TCP/UDP|Vídeo|34|Assured Forwarding (AF41)|
| 50,040 – 50,059|TCP/UDP|Compartilhamento de aplicativo/área de trabalho|18|Assured Forwarding (AF21)|

Esteja ciente dos seguintes quando você usa as informações na tabela 3:

-  Se você pretende implementar ExpressRoute no futuro e ainda não foi implementado QoS, recomendamos que você siga as orientações na tabela 3 para que os valores DSCP são os mesmos do remetente para o receptor. 

-  Todos os clientes, incluindo clientes móveis e dispositivos de equipes, usarão esses intervalos de porta e serão afetados pela implementar qualquer política DSCP que usa esses intervalos de porta de origem. Os únicos clientes que continuarão a usar portas dinâmicas são os clientes baseados em navegador (ou seja, os clientes que permitem que os participantes participar de reuniões usando seus navegadores).

-  Embora o cliente do Mac usa os mesmos intervalos de porta, ele também usa valores codificados para (EF) de áudio e vídeo (AF41). Esses valores não são configuráveis.


## <a name="source-ports-used-by-teams"></a>Portas de origem usadas pelo Microsoft Teams

No Microsoft Teams, a QoS deve ser configurada com base nas portas de origem usadas pelas diferentes cargas de trabalho. Atualmente, nenhum dos intervalos de porta do servidor nem do cliente são configuráveis. 

Os intervalos de porta de origem do cliente listados na tabela 3 também se aplicam às equipes e usam suas marcações de QoS DSCP associadas.

O método recomendado de implementação essas políticas de QoS é usar as portas de origem do cliente com um endereço IP de origem e destino de "Nenhum". Isso irá capturar ambas tráfego de mídia de entrada e saída na rede interna. 

> [!NOTE]
> Se você já tiver configurado a QoS com base em intervalos de porta de origem para Skype para Business Online, a mesma configuração será aplicada às equipes e nenhuma alteração será necessária. Se você implantou Skype para Business Server local, você precisará reexaminar suas políticas de QoS e ajustá-las, se necessário.

## <a name="set-dscp-markings"></a>Definir as marcações de DSCP

Há várias abordagens para definir as marcas de DSCP apropriadas para a classificação de tráfego:

-  **a marcação DSCP no ponto de extremidade:** Isso geralmente é a opção preferencial, porque o ponto de extremidade próprio fornece as marcações adequadas. No momento isso pode ser feito usando-se um objeto de diretiva de grupo, mas só pode ser usado em clientes do domínio Windows. Clientes móveis não fornecem um mecanismo para marcar o tráfego usando valores DSCP. Embora você não pode definir não&ndash;clientes associados a um domínio do Windows ao tráfego de marca, clientes como o Mac OS ter codificadas marcas e sempre será marcar tráfego conforme descrito acima.

-  **Usando listas de controle de acesso (ACLs) em roteadores de marcação de DSCP baseados na porta:** Essa é uma opção muito comuns encontrada em ambientes Windows e Mac heterogêneos. Neste cenário, a equipe de rede marca o tráfego nos roteadores de entrada/saída (normalmente localizado na rede de longa distância) com base nos intervalos de porta de origem definidos para cada modalidade. Embora isso funcione em todas as plataformas, ele marca somente o tráfego da borda de WAN — não totalmente para a máquina cliente — e, portanto, gera sobrecarga de gerenciamento.

-  **Uma combinação de marcações de DSCP no ponto de extremidade e baseados na porta ACLs em roteadores:** Recomendamos esta combinação, se possível em seu ambiente. Use um objeto de diretiva de grupo para capturar a maioria dos clientes e também utilizar para garantir que mobile, Mac e outros clientes ainda obterão tratamento de QoS (pelo menos parcialmente) de marcação de DSCP baseados na porta.

Você pode usar a QoS baseada em diretivas dentro da diretiva de grupo para definir o valor DSCP para o intervalo de porta de origem predefinidos no cliente equipes. Use os intervalos de porta especificados na tabela 3 para criar uma política para cada carga de trabalho.

Depois que você identificou os intervalos de porta, a próxima etapa é definir as configurações de QoS baseada em diretivas dentro de um objeto de diretiva de grupo. Você pode encontrar mais informações sobre essas etapas na [configuração de intervalos de porta e uma política de qualidade de serviço para seus clientes em Skype para Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10).

Para criar uma política de QoS de áudio para computadores Windows 10, primeiro faça logon em um computador no qual o gerenciamento de diretiva de grupo tenha sido instalado. Abra Gerenciamento de diretiva de grupo (clique em Iniciar, aponte para ferramentas administrativas e clique em gerenciamento de diretiva de grupo) e, em seguida, conclua as seguintes etapas:

1. Em gerenciamento de diretiva de grupo, localize o contêiner onde a nova diretiva deve ser criada. Por exemplo, se todos os computadores cliente estão localizados em uma unidade Organizacional denominada **clientes**, a nova diretiva deve ser criada na unidade Organizacional cliente.

2. Com o botão direito do contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.

3. Na caixa de diálogo **Novo GPO** , digite um nome para o novo objeto de diretiva de grupo na caixa **nome** e clique em **Okey**.

4. Clique com o botão a política recém-criada e clique em **Editar**.

5. No Editor de gerenciamento de diretiva de grupo, expanda **Configuração do computador**, expanda **Configurações do Windows**, do mouse em **QoS baseada em política**e clique em **Criar nova política**.

6. Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor para **46**. Deixe **Especificar taxa de aceleração saída** desmarcada e clique em **Avançar**.

7. Na próxima página, certifique-se de que **todos os aplicativos** está selecionada e clique em **Avançar**. Essa configuração instrui a rede para procurar todos os pacotes com uma marcação de DSCP 46, não apenas de pacotes criados por um aplicativo específico.

8. Na terceira página, certifique-se de que **qualquer endereço IP de origem** e de **qualquer endereço IP de destino** estão marcada e clique em **Avançar**. Estas duas configurações Certifique-se de que os pacotes serão gerenciados independentemente do computador (endereço IP) enviadas os pacotes e qual computador (endereço IP) receberá os pacotes.

9. Na página quatro, selecione **TCP e UDP** da lista suspensa **, selecione o protocolo que essa política de QoS se aplica** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados.

10. Sob o título, **Especifique o número da porta de origem**, selecione **este ou intervalo de porta de origem**. Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservadas portas 50000 através de portas 50019 para tráfego de áudio, insira o intervalo de portas usando este formato: **50000:50019**. Clique em **Concluir**.

As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada em seus computadores cliente. Embora a diretiva de grupo for atualizada periodicamente por si só, você pode forçar uma atualização imediata.

### <a name="force-group-policy-refresh"></a>Atualização de diretiva de grupo Force

1. Em cada computador para o qual você deseja atualizar a diretiva de grupo, abra um console de comando. Certifique-se de que o console de comando está definido para executar como administrador.

2. No prompt de comando, digite:
   ```
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verifique se as marcações de DSCP no objeto de diretiva de grupo

Para verificar se os valores do objeto de diretiva de grupo foram definidos, execute as seguintes etapas.

1. Abra um console de comando. Certifique-se de que o console de comando está definido para executar como administrador.

2. No prompt de comando, digite: 
   ```
   gpresult /R > gp.txt
   ```

   Isso irá gerar um relatório e enviá-la para um arquivo de texto chamado GP. txt. Como alternativa, você pode inserir o seguinte comando para produzir os mesmos dados em um relatório HTML mais legível chamado gp.html:
   ```
   gpresult /H >gp.html
   ```
 ![Captura de tela da janela do console, executando o comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de tela da janela do console, executando o comando gpresult.")

3. No arquivo gerado, procure por título de **Objetos de diretiva de grupo aplicados** e verifique se os nomes dos objetos de diretiva de grupo criados anteriormente estão na lista de diretivas aplicadas. 

4. Abra o Editor do registro e vá para:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Verifique se os valores para as entradas do Registro listadas na tabela 4.

   _Tabela 4. Valores para entradas de registro do Windows para QoS_


   |          Nome          |  Tipo  |    Dados     |
   |------------------------|--------|-------------|
   |    Nome do Aplicativo    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP Local        | REG_SZ |     \*      |
   | Comprimento do Prefixo IP Local | REG_SZ |     \*      |
   |       Porta Local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP Remoto        | REG_SZ |     \*      |
   |    Prefixo IP remoto    | REG_SZ |     \*      |
   |      Porta Remota       | REG_SZ |     \*      |
   |     Taxa de Aceleração      | REG_SZ |     -1      |


5. Verificar se o valor para a entrada de nome do aplicativo está correto para o cliente que você está usando e verificar que o valor DSCP e a porta Local entradas reflitam as configurações no objeto de diretiva de grupo.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Validar a QoS ao analisar o tráfego de equipes na rede

Para QoS para serem eficientes, o DSCP valor definido pelo objeto de diretiva de grupo deve estar presente em ambas as extremidades de uma chamada. Examinando o tráfego gerado pelo cliente equipes, verifique se o valor DSCP não será alterado ou retirado quando o tráfego de carga de trabalho de equipes percorre movimentações através da rede.

De preferência, você capturar o tráfego no ponto de saída de rede. Você pode usar o espelhamento de porta em um comutador ou roteador para ajudá-lo com isso.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Use o Monitor de rede para verificar os valores DSCP

Monitor de rede é uma ferramenta que você pode [fazer o download da Microsoft](https://www.microsoft.com/download/4865) para analisar o tráfego de rede.

1. No PC executando o Monitor de rede, conecte-se à porta que foi configurada para o espelhamento de porta e iniciar a captura de pacotes. 

2. Fazer uma chamada usando o cliente de equipes. Certifique-se de mídia foi estabelecida antes de desligar a chamada. 

3. Pare a captura.

4. No campo de **Filtro de exibição** , use o endereço IP de origem do PC que fez a chamada e refinar o filtro definindo o valor DSCP 46 (hex 0xb8) como critérios de pesquisa, conforme mostrado no exemplo a seguir:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Captura de tela da caixa de diálogo de filtro de exibição no Monitor de rede, mostrando os filtros a serem aplicados.] (media/Qos-in-Teams-Image4.png "Captura de tela da caixa de diálogo de filtro de exibição no Monitor de rede, mostrando os filtros a serem aplicados.")

5. Selecione **Aplicar** para ativar o filtro.

6. Na janela de **Quadro de resumo** , selecione o primeiro pacote UDP.

7. Na janela **Detalhes do quadro** , expanda o item de lista de IPv4 e observe o valor no final da linha que começa com **DSCP**. 

    ![Captura de tela da caixa de diálogo Detalhes do quadro no Monitor de rede, as configurações de DSCP de realce.] (media/Qos-in-Teams-Image5.png "Captura de tela da caixa de diálogo Detalhes do quadro no Monitor de rede, as configurações de DSCP de realce.")

Neste exemplo, o valor DSCP é definido como 46. Isso está correto, porque a porta de origem usada é 50019, que indica que isso é uma carga de trabalho de voz. 

Repita a verificação para cada carga de trabalho que foi marcada pelo GPO. 

## <a name="more-information"></a>Mais informações

[Preparo da rede da sua organização para o Microsoft Teams](prepare-network.md)

[Requisitos de ExpressRout QoS](https://docs.microsoft.com/azure/expressroute/expressroute-qos)