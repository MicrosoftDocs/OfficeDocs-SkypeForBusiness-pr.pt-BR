---
title: ExpressRoute e QoS no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 'Learn about using Azure ExpressRoute to have a network with bandwidth requirements and Quality of Service capability for a business class user experience. '
ms.openlocfilehash: 32d9a3f6be35077f274f0a8ab9facc462a3fe6b4
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729780"
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute e QoS no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Conexão para Microsoft 365 ou Office 365 uma conexão de rede dedicada usando o Azure ExpressRoute para Microsoft 365 ou Office 365 e Skype for Business Online. A conexão dedicada para seus aplicativos do Skype for Business oferecerá um desempenho confiável e previsível, bem como privacidade longe da Internet pública. Agora você pode comprar uma melhor conexão de rede para Microsoft 365 ou Office 365 e Skype for Business Online que adiciona previsibilidade, confiabilidade de classe empresarial e vem com um SLA de tempo de atividade.
  
> [!NOTE]
> Uma nova versão da calculadora de largura de banda está disponível: [Skype for Business, Calculadora de Largura de Banda.](https://go.microsoft.com/fwlink/?LinkId=715766) No entanto, as instruções neste documento usam a Calculadora de Largura de Banda do Lync 2010 e 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype for Business Online e ExpressRoute

Trabalhando com um parceiro ExpressRoute da Microsoft, você pode conectar uma variedade de aplicativos Microsoft 365 e Office 365, incluindo o Skype for Business Online na nuvem por uma conexão dedicada. No entanto, os recursos de comunicações de voz e vídeo em tempo real para Skype for Business exigem serviços de rede especificamente configurados para dar suporte a essas cargas de trabalho Microsoft 365 ou Office 365 em tempo real. Isso inclui uma rede com largura de banda suficiente para transportar o volume de tráfego necessário e que pode dar suporte a Qualidade de Serviço (QoS) para oferecer uma experiência de classe empresarial aos usuários.
  
Este documento foi elaborado para ajudar vocês, administradores e designers de rede, a compreender os desafios específicos necessários para dar suporte a comunicações em tempo real, as ferramentas fornecidas pela Microsoft para ajudar a criar uma rede capaz de suportar esses requisitos e orientar você pelo processo de design usando um estudo de caso. 
  
A primeira parte deste documento mostra um estudo de caso para ajudá-lo com o design de rede usando a [Calculadora de largura de banda do Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkId=690282) para calcular os requisitos de rede para uma implantação grande do ExpressRoute do Skype for Business. A segunda parte deste documento apresenta os conceitos fundamentais de Qualidade de Serviço (QoS), uma imersão profunda nos detalhes técnicos específicos para dar suporte a comunicações do Skype for Business em tempo real e os tipos específicos de serviços de rede necessários.
  
Todas as informações contidas aqui fornecerão os detalhes técnicos e o entendimento da QoS e do ExpressRoute, uma compreensão dos desafios específicos que você enfrentará e fornecerão um conhecimento prático das ferramentas e das técnicas que permitirão a implantação de um ExpressRoute com êxito em sua rede do Skype for Business. 
  
## <a name="getting-started"></a>Introdução

Ao se preparar para implantar o ExpressRoute no Skype for Business, é uma boa ideia rever os vários modelos de conexão do ExpressRoute e as diversas escolhas de parceiros e locais, além de ler sobre como adquirir e fornecer o ExpressRoute em sua empresa. Vejamos alguns recursos para você começar: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Preços do ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentação do ExpressRoute](/azure/expressroute/)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Parte 1: estudo de caso - ExpressRoute para Dewey Law, LLC.

Este estudo de caso sobre a Dewey Law, LLC. mostrará como configurar uma rede, solicitar serviços de acesso à rede e determinar os requisitos de largura de banda para dar suporte ao ExpressRoute para Skype for Business Online.
  
 **Histórico** A Dewey Law LLC. é um grande escritório de advocacia nacional com 790 advogados e um total de 5.580 funcionários espalhados em 78 locais. O escritório tem uma sede em Nova York, três escritórios regionais em Chicago, São Francisco e Dallas, juntamente com 24 filiais grandes e 50 pequenas espalhadas por todo o país. Ele lida com casos grandes e complexos, e a carga de trabalho normalmente fica espalhada entre dois ou mais escritórios. Esse design de rede resulta em uma quantidade considerável de tráfego de rede entre os escritórios.
  
A Dewey Law LLC. é uma empresa relativamente nova, os advogados e outros membros da equipe sentem-se muito confortáveis com a tecnologia e dependem bastante dela para suas tarefas diárias. 
  
 **Distribuição de usuários por locais e posições**
  
|Equipe |**Sede (NY)**|**Escritórios regionais (3)**|**Filiais grandes (24)**|**Filiais pequenas (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Executivos  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Parceiros  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Associados  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Assistentes jurídicos  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Administradores executivos  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|Administradores gerais e de TI  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Total por site  <br/> |1.070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Total por classe de site  <br/> |1.070  <br/> |1.035  <br/> |1.680  <br/> |1.800  <br/> |
   
### <a name="setting-up-the-network"></a>Configurar a rede

Para oferecer serviços em tempo real consistentes e de alta qualidade para a Dewey Law LLC., alguns requisitos básicos devem ser atendidos:
  
- Eles querem fornecer serviços de voz durante faltas de energia. Por isso, os roteadores e switches de distribuição de rede devem fornecer energia através do cabo Ethernet (PoE) IEEE 802.3af ou 802.3at.
    
- Os switches de rede e roteadores também devem usar fontes de alimentação ininterruptas (UPS) para continuar em funcionamento durante uma falta de energia.
    
    Eles têm uma Wi-Fi de conexão com seus escritórios lan, portanto, é altamente recomendável que eles usem um parceiro de infraestrutura de Skype for Business Wi-Fi certificado da [Skype for Business Solutions](https://go.microsoft.com/fwlink/?LinkId=690281).
    
    > [!TIP]
    >  [!DICA] Recomentamos pontos de acesso sem fio 802.11n e 802.11ac.
  
- E o mais importante, todas as redes LAN de todos os escritórios devem ser configuradas para oferecer Qualidade de Serviço (QoS). Isso inclui computadores, notebooks e quaisquer hardwares de rede, como switches e roteadores.
    
Agora que cobrimos o básico, para oferecer serviços de voz de nível empresarial para a Dewey Law LLC., recomendamos o uso de serviço IP MPLS (Multi-Protocol Label Switching) de um parceiro de serviços de rede que se conecta ao serviço Azure ExpressRoute. O MPLS fornece ao serviço IP uma garantia de bom desempenho contra atraso, tremulação e perda de pacotes. No entanto, se o MPLS não estiver disponível, você também pode usar um cabo Ethernet conectado a um de nossos parceiros de troca de dados do ExpressRoute.
  
Provedores de MPLS oferecem vários níveis de classe de serviço, mas cada um usa termos diferentes para identificá-los. Você terá que trabalhar de perto com seu provedor para garantir que eles entendam os dados que você tem entrada na Calculadora de Largura de Banda do [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e as opções disponíveis e são recomendadas para os diferentes aplicativos de carga de trabalho de Microsoft 365 e Office 365 em tempo real.
  
Há duas opções para como os dados de aplicativos do Skype for Business podem ser mapeados para a classe de serviço correta do MPLS:
  
- Marcação de tráfego no ponto de extremidade usando Ponto de controle DiffServ (DSCP)
    
- Com base em Lista de controle de acesso à rede (ACL)
    
Para implantar a marcação no ponto de extremidade, você deve configurar todos os computadores com Windows que fizerem parte do domínio da Dewey Law LLC. para marcar cada pacote com a marcação de Ponto de controle DiffServ (DSCP) adequada e, em seguida, implantar a QoS em todos os switches de rede e roteadores de todos os escritórios para garantir que as marcações de QoS sejam mantidas e não sejam removidas. Marcações de DSCP nos pacotes de rede indicam para o provedor de serviços qual a prioridade daquele pacote. **Há mais informações sobre o DSCP na seção QoS, na Parte 2.**
  
Para atribuição baseada em ACL de rede, as marcações de prioridade de DSCP são implantadas em um roteador upstream e têm como base a porta de origem UDP. Os intervalos de porta recomendados para cada aplicativo estão listados na Seção 2.6.1.1 de Planejamento, Monitoramento e Solução de Problemas de Rede com [o Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286). É importante coordenar isso com a implantação e o projeto de QoS geral da Dewey Law LLC, além de estar ciente das diferentes políticas de QoS e do potencial para discrepâncias nas marcações de pacotes.
  
Cada provedor de serviços de rede do ExpressRoute terá uma classe de serviço (QoS) adequada para voz e vídeo em tempo real. Essa COS é chamada de "Expedited Forwarding" (EF) para voz e "Assured Forwarding" (AF) para vídeo. É preciso muito cuidado para dimensionar a quantidade de largura de banda adquirida para tráfego de EF de voz. Isso porque a classe de serviço de voz não aceita enviar mais tráfego de voz do que ela foi projetada para enviar.
  
> [!TIP]
>  [!DICA] Qualquer tráfego enviado pela classe de serviço de voz que ultrapasse a quantidade fornecida pelo provedor de serviços será descartado imediatamente, o que afetará diretamente a qualidade de voz.
  
Ao analisar o projeto geral da Dewey Law LLC., é extremamente importante determinar com precisão a quantidade de largura de banda de rede necessária para dar suporte ao tráfego de voz em toda a rede e marcar cada pacote de voz (e somente os pacotes de voz) com a configuração de DSCP para voz (ou seja, DSCP EF 46).
  
Para implementar a QoS em sua rede corporativa, os pontos de extremidade ou roteadores devem marcar cada pacote com o indicador de prioridade da Camada 3 apropriado (ou seja, DSCP). Cada switch e roteador na rede deve ter a opção QoS ativada. Se um único switch de rede ou roteador não tiver QoS ativada, as marcações QoS nos pacotes de voz ou vídeo que passarem por esse switch ou roteador podem ser removidas. Isso efetivamente desativa a QoS em todos os switches e roteadores seguintes, o que diminui o valor de ter o ExpressRoute.
  
Isso também exige que as associações de prioridade de QoS na Camada 3 e Camada 2 sejam definidas em cada ponto. Os mecanismos de prioridade da Camada 2 são definidos em IEEE 802.1p para redes com fio e em 802.11e/WMM para redes Wi-Fi. Mais importante ainda, o roteador de rede voltado para o provedor de serviços da rede MPLS deve manter as configurações de DSCP em todos os pacotes de saída, a fim de manter a classe de serviço MPLS adequada. 
  
> [!TIP]
>  Para obter os detalhes específicos sobre a configuração de QoS, consulte Section 2.6 [Network Planning, Monitoring, and Troubleshooting with Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669). Você também pode consultar [Planejar os requisitos de rede para o Skype for Business 2015](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) para ver mais requisitos do planejamento de rede.
  
### <a name="ordering-network-access-services"></a>Solicitar serviços de acesso à rede

Depois de preparar os pré-requisitos de rede de QoS e os mecanismos necessários para dar suporte ao ExpressRoute, a próxima etapa é solicitar os serviços de acesso à rede do ExpressRoute. Ao solicitar serviços de acesso à rede do ExpressRoute para a Dewey Law LLC do provedor de serviços de rede parceiro da Microsoft, será necessário fornecer duas coisas:
  
- A quantidade total de largura de banda necessária para conectar cada site ao ExpressRoute e Microsoft 365 ou Office 365.
    
- A largura de banda total necessária para cada classe de serviço necessária para dar suporte aos aplicativos do Skype for Business que forem usados na Dewey Law LLC. Os requisitos de largura de banda para classe de serviço são definidos pelo volume de tráfego esperado para cada uma das várias aplicações do Skype for Business, como voz, vídeo, mensagens instantâneas, presença e compartilhamento de tela.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Determinar os requisitos de largura de banda para as aplicações do Skype for Business

Para a Dewey Law LLC., depois de determinar a largura de banda total necessária, você precisa saber como essa quantidade total de largura de banda deve ser dividida entre as várias classes de serviço. Por exemplo, quanta largura de banda cada aplicação do Skype for Business exige.
  
Para determinar esses requisitos em cada um dos locais da Dewey Law LLC., use a [Calculadora de largura de banda do Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282). Essa calculadora é uma ferramenta baseada em Excel que permite especificar o uso esperado das várias aplicações do Skype for Business, incluindo voz, vídeo, conferência e compartilhamento de tela. A calculadora automaticamente gerará uma estimativa da largura de banda e dos requisitos de CoS para cada local em sua rede. Ao fazer o download da Calculadora de largura de banda do Lync 2010 e 2013, um guia do usuário também será baixado para oferecer detalhes sobre o uso. 
  
Para ajudar, as diferentes células da planilha são codificadas por cores:
  
- **Verde** São as áreas de entrada de dados gerais.
    
- **Amarelo** São as áreas de entrada de dados avançados. Você pode alterá-las, mas tenha cuidado.
    
- **Vermelho** São as áreas somente para leitura, com valores de entrada fixos que não podem ser alterados.
    
- **Cinza** São as áreas apenas para exibição. São os resultados dos dados inseridos nas áreas de entrada gerais.
    
O processo de design da Dewey Law LLC. começa com a caracterização dos usuários em diferentes "personas". Para cada persona definida, você pode especificar o uso previsto dos vários aplicativos do Skype for Business ("Nenhum", "Baixo", "Médio", "Alto" ou uma de três configurações "Personalizadas" definidas). Essas seleções podem ser encontradas na planilha "Persona". O uso específico de cada opção ("Baixo", "Médio" ou "Alto") é fornecido, mas os padrões de cada opção podem ser alterados. Ao identificar o número de usuários de cada persona em cada local, a calculadora pode calcular a largura de banda total necessária para cada local.
  
Você também pode especificar os codecs de áudio e vídeo usados, se a correção de erro antecipada é usada e também outros parâmetros do sistema que afetarão os requisitos de largura de banda. Você pode usar as configurações padrão da Calculadora de largura de banda do Lync 2010 e 2013 ou selecionar codecs diferentes e outros parâmetros do sistema. Para o projeto do local da Dewey Law LLC, as configurações padrão podem ser usadas. No entanto, caso você queira alterar alguma das configurações padrão, há um menu suspenso disponível com todas as opções disponíveis. As larguras de banda usadas para cada opção são incluídas na planilha "Codecs". Quando você alterar qualquer configuração, a alteração na relação entre largura de banda e classe de serviço (CoS) em cada local é atualizada. Esse recurso permite testar diferentes configurações possíveis para os locais e ver o impacto que as alterações terão nos requisitos de largura de banda.
  
Definimos três personas para a Dewey Law LLC.: "Executivos/Parceiros", "Associados/Assistentes jurídicos" e "Administradores de TI". A tabela abaixo mostra como definimos os perfis de uso para os vários aplicativos do Skype for Business em cada persona.
  
 **Personas e perfis de uso (Planilha "Persona": Colunas A a P)**
  
|**Pessoal**|**Mensagens Instantâneas/Presença**|**Áudio P2P**|**Vídeo P2P**|**Áudio da conferência**|**Vídeo da conferência**|**Compartilhamento da área de trabalho**|**Audioconferência**|**Lync 2010 RTV_Type**|**Usuários remotos**|**Lync 2013 áudio estéreo**|**Lync 2013 qualidade de vídeo**|**Lync 2013 comportamento dos usuários para janela de vídeo P2P**|**Lync 2013 Uso de Multi-view**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Executivos/ Parceiros  <br/> |Alto  <br/> |Médio  <br/> |Baixo  <br/> |Médio  <br/> |Médio  <br/> |Nenhum  <br/> |Médio  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Melhor  <br/> |Típico  <br/> |Típico  <br/> |
|Associados/ Assistentes jurídicos  <br/> |Alto  <br/> |Médio  <br/> |Baixo  <br/> |Médio  <br/> |Alto  <br/> |Alto  <br/> |Médio  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Médio  <br/> |Típico  <br/> |Típico  <br/> |
|Administradores de TI  <br/> |Alto  <br/> |Médio  <br/> |Nenhum  <br/> |Baixo  <br/> |Nenhum  <br/> |Nenhum  <br/> |Médio  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Médio  <br/> |Típico  <br/> |Típico  <br/> |
   
Será necessário digitar as informações na tabela **Distribuição de usuários por locais e posições** acima na planilha "Locais" da Calculadora de largura de banda do Lync 2010 e 2013. Como o número de usuários nos escritórios regionais é idêntico, eles são definidos para um "Local" e especificamos que existiam três instâncias dele. O mesmo foi feito para as filiais grandes e pequenas com 24 e 50 usuários no local, respectivamente.
  
Depois de especificar as configurações de cada persona, será preciso inserir o número de usuários de cada persona em cada local na planilha "Locais". O número total de usuários em todos os locais é atualizado automaticamente. Como não há usuários no local de Microsoft 365 ou Office 365, todos eles devem ser inseridos nas linhas "Ramificações" da planilha. A Calculadora de largura de banda do Lync 2010 e 2013 preenche as colunas "Classe de melhor esforço", "Classe de tráfego de dados" e "Classe de tráfego em tempo real " da tabela "WAN BW por classe de tráfego de QoS". Isso é mostrado nos dados da tabela abaixo.
  
> [!TIP]
>  [!DICA] A planilha completa também inclui o número máximo de sessões simultâneas para cada aplicativo, mas excluímos essas colunas para economizar espaço.
  
 **Personas por local (Planilha "Locais": Colunas A, D, I e AI até AX)**
  
|**Nome do local**|**Total de usuários no local**|**Total de locais como esse**|**Perfil de usuário 1**|**Usuários no Perfil 1**|**Perfil de usuário 2**|**Usuários no Perfil 2**|**Perfil de usuário 3**|**Usuários no Perfil 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede  <br/> |1070  <br/> |1  <br/> |Executivos/Parceiros  <br/> |170  <br/> |Associados/Assistentes jurídicos  <br/> |700  <br/> |Administradores de TI  <br/> |200  <br/> |
|Escritórios regionais  <br/> |345  <br/> |3  <br/> |Executivos/Parceiros  <br/> |60  <br/> |Associados/Assistentes jurídicos  <br/> |225  <br/> |Administradores de TI  <br/> |60  <br/> |
|Filiais grandes  <br/> |70  <br/> |24  <br/> |Executivos/Parceiros  <br/> |11  <br/> |Associados/Assistentes jurídicos  <br/> |50  <br/> |Administradores de TI  <br/> |9  <br/> |
|Filiais pequenas  <br/> |36  <br/> |50  <br/> |Executivos/Parceiros  <br/> |6  <br/> |Associados/Assistentes jurídicos  <br/> |25  <br/> |Administradores de TI  <br/> |1  <br/> |
   
 **Largura de banda necessária por aplicativo por local, em Kbps (Planilha "Locais": Colunas A e BQ até LF)**
  
|**Site**|**Largura de banda de pico de SIP/IM**|**Largura de banda de pico para áudio de par entre sites**|**Largura de banda de pico para vídeo de par entre sites**|**Largura de banda de Conferência de Áudio de Pico**|**Largura de banda de Conferência de Vídeo de Pico**|**Largura de banda de pico para compartilhamento de WAN**|**Largura de banda de pico de WAN para chamadas PSTN**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Escritórios regionais  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Filiais grandes  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |
|Filiais pequenas  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |
   
Provavelmente, as colunas mais importantes da planilha são aquelas que descrevem a largura de banda de WAN por classe de QoS. Isso é mostrado na tabela abaixo. Esses dados resumem as informações que você precisará fornecer para o provedor de serviços de rede para solicitar a conexão de acesso em cada um dos seus sites. Ao calcular a largura de banda total, lembre-se de multiplicar a largura de banda para cada tipo de site de filiais pelo número de sites do mesmo tipo. Para conectar-se com seu parceiro de serviços de rede do ExpressRoute, você pode usar o [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
É muito importante não exceder a largura de banda na classe de serviço de voz ou "Expedited Forwarding" (EF). Um conjunto aleatório de pacotes será descartado. Por isso, em vez de reduzir a qualidade de uma única chamada ou grupo de chamadas, todas as chamadas em curso podem ser afetadas. Também é importante que somente pacotes de voz sejam marcados com DSCP para EF (ou seja, DSCP = 46), caso contrário, a fila poderá exceder o limite quando outros tipos de tráfego forem adicionados.
  
> [!TIP]
>  [!DICA] Novamente, embora a classe de serviço EF ofereça a melhor garantia de desempenho, se você exceder a largura de banda definida os pacotes adicionais serão descartados imediatamente.
  
 **Agregar largura de banda por site por classe de tráfego QoS - (Planilha de Sites- Colunas A e ML por MR)**
  
|**Nome do local**|**Classe de melhor esforço (DSCP 0)**|**Classe de tráfego de dados (DSCP personalizado)**|**Classe de tráfego em tempo real (DSCP 34, AF41)**|**Classe de tráfego prioritário (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Sede  <br/> |0.00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Escritórios regionais  <br/> |0.00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Filiais grandes  <br/> |0.00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Filiais pequenas  <br/> |0.00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Colocar o plano em ação

Podemos calcular a largura de banda total que atravessará a WAN e a quantidade de largura de banda que atravessará o ExpressRoute, usando as estimativas de largura de banda a partir da tabela **Por aplicativo por site** exibida acima. A parte de tráfego que atravessa o ExpressRoute exclui a largura de banda de par entre locais.

 
|**Site**|**Largura de banda de pico de SIP/IM**|**Largura de banda de Conferência de Áudio de Pico**|**Largura de banda de Conferência de Vídeo de Pico**|**Largura de banda de pico para compartilhamento de WAN**|**Largura de banda de pico de WAN para chamadas PSTN**|**Total de tráfego ExpressRoute <br/> por classe de site <br/> (ou seja, tempo total <br/> # de sites)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sede** <br/> |1.070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Escritórios regionais** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Filiais grandes** <br/> |70  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Filiais pequenas** <br/> |36  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Isso significa que o tráfego do Skype for Business Online que atravessará a rota expressa será de aproximadamente 114 Mbps, portanto Dewey precisará de pelo menos 200 Mbps de assinatura para o ExpressRoute. Vários circuitos do ExpressRoute podem ser comprados em diferentes locais de pareamento do ExpressRoute. Isso pode ser recomendável se os locais de Dewey estiverem em diferentes regiões geográficas ou para fornecer resiliência em caso de falha na conexão com o circuito do ExpressRoute. Se você adquirir os circuitos do ExpressRoute em várias regiões do Azure, o complemento ExpressRoute premium deverá receber conectividade global do ExpressRoute.
  
Agora que você tem a quantidade total de largura de banda necessária e os números de largura de banda da classe de serviço (CoS), você poderá fazer as solicitações com o(s) provedor(es) de serviço de rede selecionado(s). Não se esqueça de incluir estimativas de tráfego para outros aplicativos e serviços. Oferecemos diretrizes de planejamento de rede para outros serviços Microsoft 365 e Office 365, incluindo calculadoras de largura de banda para Exchange e OneDrive. A assinatura de largura de banda para o provedor de serviços de rede será mais alta porque o tráfego intra-site precisará ser adicionado novamente. A calculadora de largura de banda do Lync 2010 e 2013 fornece apenas uma estimativa do tráfego esperado, portanto, é recomendável confirmar a capacidade da rede em suportar esse volume de tráfego realizando um teste de estresse. 
  
> [!TIP]
> [!DICA] Testes de estresse são altamente recomendáveis ao realizar uma pré-avaliação da rede. 
  
Um teste de estresse envolve criar e configurar a infraestrutura e, em seguida, executá-la com o volume previsto de tráfego simulado enquanto monitora o desempenho. Suas estimativas de tráfego podem estar incorretas em algumas áreas, mas pelo menos você tem a certeza de que a rede pode suportar o volume de tráfego previsto pela Calculadora de largura de banda do Lync 2010 e 2013. É recomendável que você execute o teste de estresse por alguns dias, mas executá-lo durante um período mais longo pode ajudar a refinar os números. No entanto, o aumento do período do teste de estresse deve ser avaliado em relação ao custo dos serviços de rede pelos quais você está pagando e que não transportam o tráfego de rede de usuários reais. A Microsoft certificou diversos fornecedores como parte do programa IT Pro Tools para fornecer ferramentas de gerenciamento de rede e operações, incluindo ferramentas de pré-avaliação do estresse da rede. O Skype for Business também fornece um integrador de sistemas (SI) que podem usar as IT Pro Tools e fazer a avaliação da rede para você. Para ver mais informações, consulte [Soluções do Skype for Business: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
O teste de estresse fornece alguma garantia de que a rede pode suportar o volume de tráfego necessário, mas, na realidade, os dados da Calculadora de largura de banda do Lync 2010 e 2013 podem estar incorretos por diversas razões. Considere também continuar a monitorar as redes de seus locais com uma avaliação de rede constante depois da implantação para garantir que a largura de banda seja suficiente e que os mecanismos de QoS funcionem corretamente. É importante continuar a monitorar o desempenho da rede à medida que mais e mais usuários reais começam a usá-la.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Parte 2: QoS de Skype for Business do ExpressRoute

O serviço ExpressRoute da Microsoft fornece uma conexão dedicada à nuvem do Azure, mas os serviços de comunicação de cargas de trabalho em tempo real do Office 365 exigem serviços de rede com largura de banda suficiente para transportar o volume de tráfego e são capazes de oferecer suporte a QoS (Qualidade de Serviço) para proporcionar uma experiência do usuário de nível empresarial. Uma conexão com recursos de QoS deve ser configurada de ponta a ponta (PC, switches de rede e roteadores para a computação em nuvem), pois qualquer parte do caminho que não suportar QoS poderia afetar a qualidade da conversa inteira.
  
O objetivo desta seção é ajudá-lo a entender os desafios ao dar suporte ao tráfego em tempo real em uma rede IP e configurar e dar suporte a uma implantação bem-sucedida do ExpressRoute de cargas de trabalho em tempo real do Microsoft 365 ou Office 365 usando um parceiro de Provedor de Serviços de Exchange Rede ou Provedor de Serviços de Rede da Microsoft.
  
A QoS é aceita de suas redes exclusivamente por circuitos de rede ExpressRoute e é usada dentro da rede da Microsoft para o tráfego do Skype for Business. Hoje, partes de algumas conexões de saída da Microsoft têm valores de DSCP ausentes para o Skype for Business. Até o tráfego de saída ser totalmente marcado com valores de DSCP, é recomendável seguir as orientações para a adição de marcações de QoS ao tráfego no limite da sua rede, conforme descrito na seção **Como implementar QoS usando uma ACL (lista de controle de acesso) de rede** deste artigo.
  
### <a name="the-real-time-problem"></a>O problema do tempo real

Oferecer serviços de voz e vídeo com qualidade empresarial resulta em exigências especiais para uma rede IP. O tráfego em tempo real usa o protocolo RTP (Real-time Transport Protocol), que é transportado usando o protocolo UDP (User Datagram Protocol). Ao contrário do protocolo TCP (Transmission Control Protocol), que enumera e testa cada uma dessas mensagens para impedir erros e inclui outros mecanismos para detectar e retransmitir mensagens perdidas ou incorretas, o UDP não oferece esse tipo confiabilidade. Se as mensagens forem corrompidas por erros ou forem perdidas devido a estouros de buffer, serão perdidas. O UDP foi escolhido para uso com RTP porque a natureza do tráfego em tempo real é que, mesmo se as mensagens perdidas forem reenviadas, elas chegariam tarde demais para ter um impacto positivo no fluxo da mensagem de voz.
  
Sabendo o impacto da perda de pacotes de voz, os designers de rede chegaram a duas abordagens para melhorar o desempenho de voz e vídeo sobre IP:
  
- Tornar a codificação/decodificação de voz mais resiliente quando os pacotes são perdidos. Isso pode ser feito usando a correção de erro de encaminhamento (FEC) para corrigir uma porcentagem dos erros encontrados, que é uma funcionalidade encontrada no transporte de tempo real do Microsoft 365 ou do Office 365 ou projetando sistemas de decodificação de voz que tentam mascarar o efeito de pacotes perdidos, que é uma característica dos codecs da Microsoft. 
    
- Use serviços de transporte que têm mecanismos de qualidade de serviço para garantir o desempenho da rede em relação a atrasos, perda de pacotes, tremulação e variação de atraso entre os pacotes.
    
Uma codificação de voz resiliente só aborda o problema de perda de pacotes. Por isso, é importante que a rede usada para transportar voz e vídeo em tempo real tenha mecanismos para minimizar atrasos e tremulação. Mesmo com a codificação resiliente, se muitos pacotes forem perdidos a estação receptora não terá informações suficientes para reconstruir uma versão reconhecível do sinal de voz. A porcentagem de pacotes perdidos que resultaria em uma degradação perceptível da qualidade de voz varia dependendo da técnica de codificação de voz usada. No entanto, em todos os casos, perder cadeias de pacotes sucessivas é muito problemático.
  
Minimizar o atraso é importante, porque uma demora excessiva pode afetar o fluxo da conversa e criar um aborrecimento para os usuários. As práticas recomendadas dizem que o atraso de ponta a ponta para voz (o que chamamos atraso "boca-a-ouvido") deve ser mantido abaixo de 150 milissegundos (ms) de forma unidirecional, não "ida e volta". É evidente que o atraso aumentará em ligações de transmissão maiores, como as que atravessam oceanos, dado o atraso de propagação ou o tempo que leva para o sinal viajar fisicamente pelo cabo.
  
Quando o intervalo fica acima de 150 ms em uma direção, ele tem um efeito de estranheza no falante. Psicologicamente, um relógio dispara no cérebro do falante, que o leva a pensar que o destinatário não ouviu e que ele precisa repetir a última frase. Essa fala colide com a resposta atrasada que vem da outra ponta. Se você já conversou por meio de um canal de satélite, reconhece esse efeito. Em um canal de satélite, o atraso unilateral é de aproximadamente 250 ms, que ultrapassa muito o atraso permitido.
  
 **Parâmetros de rede recomendados para voz de nível empresarial**
  
|**Parâmetro**|**Valor recomendado**|
|:-----|:-----|
|Tremulação do pacote entre chegadas (média)  <br/> |≤ 5 ms  <br/> |
|Tremulação do pacote entre chegadas (máxima)  <br/> |≤ 40 ms  <br/> |
|Taxa de perda de pacotes (média)  <br/> |Próxima de 0%  <br/> |
|Latência unilateral da rede  <br/> |≤ 100 ms (deve incluir verificações do atraso em relação à distância geográfica)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute como parte de uma rede de voz de nível empresarial

O ExpressRoute oferece uma conexão dedicada por meio de um Provedor de Serviços de Rede (NSP) ou um Provedor do Exchange (EXP) em uma das 3 opções de conexão: 
  
- Localização do Exchange na Nuvem
    
- Conexão Ethernet Ponto-a-ponto
    
- Conexão de qualquer ponto a qualquer ponto (IPVPN)
    
Proporciona benefícios de alta disponibilidade (99,9% de SLA de disponibilidade) roteamento confiável e seguro (sem trânsito de internet), não é afetada por variações de tráfego da Internet e respeita as marcações de Qualidade de Serviço para priorizar o tráfego (o QoS é explicado abaixo). O ExpressRoute, juntamente com uma WAN bem planejada, pode oferecer uma rede de voz de nível empresarial.
  
Você pode usar o ExpressRoute para o trânsito de dados de escritórios ou datacenters (no caso de topologia híbrida) que estão conectados ao circuito. Dados para usuários externos (por exemplo, de escritórios residenciais ou viajando, etc.) não serão úteis para o circuito do ExpressRoute, a menos que os usuários tenham conexão VPN e não precisem ser incluídos em estimativas de largura de banda para dimensionar o circuito do ExpressRoute. Se você for um cliente multinacional, você poderá comprar os circuitos do ExpressRoute em cada região e usar as marcas da comunidade BGP para informar regras de roteamento de forma que o tráfego seja direcionado para o circuito preferencial do ExpressRoute (normalmente o mais próximo de cada local), enquanto os outros circuitos oferecem redundância no caso de paralisação afetar um único circuito. 
  
### <a name="if-expressroute-isnt-an-option"></a>Se o ExpressRoute não for uma opção

Talvez não seja viável conectar todos os sites ao ExpressRoute devido aos custos, à incapacidade de atender a todos os seus requisitos ou limitações do seu NSP atual. Se você não puder usar o ExpressRoute, ainda recomendamos seguir as orientações abaixo para marcar a QoS em sua rede e planejar os contratos com seu NSP para garantir que haja largura de banda suficiente e suporte para a priorização do tráfego com base na QoS.
  
Além disso, se você tiver escritórios em várias regiões, mas não tiver circuitos ExpressRoute em todas as regiões, deverá usar as marcas da comunidade BGP regionais ao configurar o roteamento para o tráfego de/para escritórios satélites, de forma que o uso desnecessário de trânsito de longo curso possa ser evitado. Por exemplo, considere uma empresa que tenha uma organização do Skype for Business Online hospedada nos Estados Unidos, mas com filiais na Europa, e a empresa tenha apenas um único circuito ExpressRoute no Vale do Silício. A maior parte do tráfego do Skype for Business Online será encaminhada para um data center onde a organização esteja hospedada (por exemplo, chamadas em conferência com outros usuários dentro da empresa), e a utilização do circuito ExpressRoute pode ser preferida para a maior parte do tráfego. No entanto, se um usuário na Europa ingressasse em uma chamada em conferência hospedada por outra empresa cuja organização está localizada na Europa, o destino de mídia daquela chamada seria o data center europeu onde a segunda empresa está localizada. O roteamento do tráfego por meio do circuito ExpressRoute no Vale do Silício seria uma rota menos direta do que a possível pela Internet. Nesse caso, convém configurar os roteadores na sua rede (por exemplo, em escritórios da Europa) para inspecionar as marcas da comunidade ao fazer regras de roteamento, bem como o roteamento pela Internet em vez do circuito ExpressRoute no Vale do Silício para o tráfego que tenha marcas regionais europeias.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Conceitos básicos de Qualidade de Serviço (QoS)/Classe de serviço (CoS)

Em IP, QoS (Qualidade de Serviço) descreve qualquer mecanismo usado para fornecer atendimento prioritário a alguns pacotes. Segundo a definição da União Internacional de Telecomunicações (ITU), a QoS compreende todos os aspectos de qualidade de uma conexão, incluindo atraso, perda de pacotes, relação sinal/ruído, diafonia, interrupções, resposta de frequência, níveis de altura e assim por diante. Um termo mais correto para o que chamamos de QoS em redes de pacotes seria Classe de serviço (CoS), que se concentra em melhorar o desempenho com relação a atrasos, tremulação e perda de pacotes, mas vamos continuar a usar o termo QoS, pois é o mais usado.
  
Fornecer QoS a uma rede IP exige dois componentes principais:
  
- A reserva de uma quantidade definida de largura de banda em cada link para tráfego em tempo real. Se essa largura de banda não for necessária para o tráfego em tempo real, ela pode ser usada para outros tipos de tráfego. A orientação geral é não atribuir mais de 30% da capacidade de qualquer link para o tráfego de voz.
    
- Marcar os pacotes com um indicador de prioridade no cabeçalho, para informar aos switches e roteadores no caminho a prioridade do pacote que deve ser atribuído.
    
Quando um pacote é recebido por um switch ou roteador, ele será movido para um fila de saída para a próxima etapa ou salto. Há diferentes filas de saída para os diferentes níveis de prioridade. Um switch ou roteador usa um algoritmo que se dedica à fila de alta prioridade com mais frequência do que as filas com prioridade mais baixa.
  
O desafio é que existem diferentes técnicas de QoS implementadas na Camada 2 (ou seja, a camada Ethernet ou Wi-Fi) e na Camada 3 (ou seja, a camada IP). Pode ser necessário configurar essas diferentes implementações de QoS em cada switch e roteador da rede, além de uma interface entre sua rede e a rede do provedor de serviços de rede.
  
Há duas opções para como os dados de vários aplicativos do Skype for Business podem ser mapeados para a classe de serviço correta:
  
- Marcação de tráfego no ponto de extremidade usando Ponto de Controle de Serviços Diferenciados (DSCP) 
    
- Com base em Lista de controle de acesso à rede (ACL)
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Marcação de tráfego no ponto de extremidade usando Ponto de Controle de Serviços Diferenciados (DSCP)

Serviços diferenciados (DiffServ) é conhecido como um mecanismo "de granulação grossa" para classificar e gerenciar o tráfego de rede e fornecer a QoS em redes IP. Os roteadores e outros dispositivos que implantam funções de Camada 3 usam o Ponto de Controle DiffServ (DSCP) para definir a prioridade do pacote. A QoS é implantada inserindo um valor DSCP de 6 bits no campo Serviços diferenciados (anteriormente conhecido como campo "Tipo de serviço") no cabeçalho IP. 6 bits permitem 64 níveis de prioridade diferentes. Os níveis de prioridade são tipicamente definidos conforme mostrado aqui.
  
 **Configurações de DSCP recomendadas**
  
|**Classe de tráfego**|**Tratamento (Marcação de DSCP)**|**Cargas de trabalho do Skype for Business**|
|:-----|:-----|:-----|
|**Voz** <br/> |EF (46)  <br/> |Skype for Business e voz do Lync  <br/> |
|**Interativo** <br/> |AF41 (34)  <br/> |Vídeo  <br/> |
||AF21 (18)  <br/> |Compartilhamento de aplicativos  <br/> |
|**Padrão** <br/> |AF11 (10)  <br/> |Transferência de arquivos  <br/> |
||CS0 (0)  <br/> |Outros  <br/> |
   
 **Header IP Versão 4**
  
![Header IPv4.](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS de Camada 2: IEEE 802.1p/Wi-Fi multimídia (IEEE 802.11e)

Embora o DSCP seja o mecanismo padrão para a implantação de QoS na Camada 3, há diferentes mecanismos de QoS na Camada 2 para redes com fio (ou seja, Ethernet) e sem fio (ou seja, redes Wi-Fi). O mecanismo de QoS para redes com fio é definido no padrão IEEE 802.1p. O mecanismo de QoS WLAN é definido no padrão IEEE 802.11e, que o Wi-Fi Alliance identifica como "Wi-Fi Multi-Media Certified" (WMM Certified).
  
O padrão IEEE 802.1p usa um Ponto de Código de Prioridade (PCP) de 3 bits para identificar a prioridade da mensagem. O PCP faz parte de um campo de 32 bits no cabeçalho Ethernet que também transporta o identificador da VLAN. As definições dos valores de PCP estão incluídos abaixo.
  
 **Valores pcp do IEEE 802.1p**
  
|**Valor do PCP**|**Prioridade**|**Acrônimo**|**Tipos de tráfego**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Controle de rede  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Controle entre redes  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Voz  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Vídeo  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Aplicativos críticos  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Esforço excelente  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |Melhor esforço  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Plano de fundo  <br/> |
   
A implantação de IEEE 802.1p funciona da mesma maneira que DSCP com tráfego organizado em diferentes filas de prioridade para cada nível de prioridade, mas a natureza de meio compartilhado das WLANs pede uma abordagem diferente. Embora o ponto de acesso e o cliente mantenham filas de saída separadas para os diferentes níveis de prioridade, também existem diferenças na forma como os quadros são enviados no canal de rádio.
  
Em uma rede Wi-Fi, todos os clientes associados a um ponto de acesso compartilham um único canal half-duplex (ou seja, apenas uma estação de cliente ou ponto de acesso pode enviar por vez). Para minimizar o potencial de colisões no canal de rádio, antes de enviar um quadro a estação aguarda o canal ficar inativo durante um intervalo chamado de "Espaçamento entre Quadros". Se o canal estiver ocupado quando uma estação tenta enviar, ela recua por um período aleatório. Quando o quadro é enviado, se o remetente não receber uma mensagem de confirmação do destinatário, a estação assume que ocorreu uma colisão ou outra falha e recua por um período aleatório antes de tentar acessar o canal de rádio para reenviar. O intervalo de recuo é aleatório para reduzir a probabilidade das mesmas duas estações colidirem novamente.
  
Para priorizar o acesso ao canal de rádio, o IEEE 802.11e/WMM define diferentes intervalos de espera pré-transmissão, chamados de "Espaçamentos Arbitrados entre Quadros" (AFIS), e diferentes intervalos de recuo para as diferentes classes de tráfego. Quatro níveis de prioridade denominados "Categorias de Acesso" são definidos.
  
A prioridade é concedida ao atribuir valores de AFIS menores para os quadros de maior prioridade. Portanto, se uma estação está aguardando para enviar um quadro de voz e outra está aguardando para enviar um quadro de dados, o quadro de voz será sempre enviado primeiro. Tecnicamente, quadros de voz e vídeo recebem os mesmos valores de AFIS, mas o intervalo de recuo para quadros de vídeo é mais alto. Assim, embora seja possível que um quadro de voz e um de vídeo colidam na primeira tentativa, o quadro de voz sempre será retransmitido primeiro. A correlação entre IEEE 802.1p e IEEE 802.11e é mostrada abaixo:
  
 **Mapeamento do IEEE 802.11e/Wi-Fi Multi-Media (WMM) a 802.1P**
  
|**Categoria de acesso à WMM**|**WMM descrição**|**Valor de PCP do 802.1p**|**Designação do 802.1p**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Voz  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Vídeo  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Melhor esforço Dados  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4 (AC_BK)  <br/> |Plano de fundo Dados  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
A associação recomendada de prioridades da Camada 3 para a Camada 2 é mostrada aqui:
  
 **Associações de prioridades recomendadas da Camada 3 para a Camada 2**
  
|&nbsp; |**Marcações da Camada 3**|**Camada 2 (Valor de PCP)**|**Wi-Fi (Categoria de acesso)**|
|:-----|:-----|:-----|:-----|
|Controle de rede  <br/> |Comportamento por salto (PHB) - Seletor de Classe (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valor de DSCP - 48  <br/> |
|Voz  <br/> |Comportamento por salto (PHB) - Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valor de DSCP - 46  <br/> |
|Videoconferência  <br/> |Comportamento por salto (PHB) - Assured Forwarding (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valor de DSCP - 34  <br/> |
|Sinalização de chamada  <br/> |Comportamento por salto (PHB) - Seletor de Classe (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valor de DSCP - 24  <br/> |
|Dados de baixa latência  <br/> |Comportamento por salto (PHB) - Assured Forwarding (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valor de DSCP -18  <br/> |
|Dados de alto rendimento  <br/> |Comportamento por salto (PHB) - Assured Forwarding (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valor de DSCP - 10  <br/> |
|Melhor esforço  <br/> |Comportamento por salto (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valor de DSCP - 0  <br/> |
   
É importante observar que há uma incompatibilidade na codificação de prioridade para IEEE 802.1p e WMM. O valor 802.1p para voz é 5, no entanto, no mapeamento de equivalência padrão para WMM, o PCP 5 é convertido para Access Category 2, a categoria de acesso WMM para vídeo (AC_VI). Se possível, você deve substituir esse mapeamento para que o PCP 5 se traduza para a Categoria 1 do Access ou simplesmente evite usar voz e vídeo na mesma rede Wi-Fi até que o Wi-Fi Alliance resolve esse problema. Para obter informações adicionais sobre Wi-Fi, consulte [Itens de Catálogo Wi-Fi.]( https://go.microsoft.com/fwlink/?LinkId=690322)
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Implantar QoS usando a Lista de controle de acesso à rede (ACL)

O método alternativo para implantar QoS em uma configuração ExpressRoute é usar a Lista de controle de acesso à rede (ACL). Nessa abordagem, em vez fazer com que todos os pontos de extremidade insiram a marcação DSCP adequada no cabeçalho de cada pacote, a marcação pode ser feita por um roteador upstream, com base na porta de origem UDP. Todos os switches e roteadores ainda precisam ser configurados para oferecer suporte a QoS para garantir que as definições de DSCP sejam mantidas. Mais importante, o roteador conectado à rede do provedor de serviços deve manter o DSCP no cabeçalho de cada pacote, pois essa configuração de DSCP é essencialmente sua instrução para o provedor de serviços de rede sobre como o pacote deve ser tratado.
  
Os intervalos de porta recomendados para cada aplicativo Skype for Business estão listados na Seção 2.6.1.1 do guia Planejamento, Monitoramento e Solução de Problemas de Rede com o [Lync Server.](https://go.microsoft.com/fwlink/?LinkId=690286) É importante que isso seja coordenado com a abordagem geral da empresa à QoS, e você deve estar atento a diferentes políticas de QoS e a possíveis divergências na remarcação dos pacotes.
  
Embora o motivo principal para QoS e serviços de rede MPLS serem usados seja para garantir uma boa experiência do usuário com voz e vídeo em tempo real, esses mesmos recursos também podem ser usados com aplicações de dados. Em vez de tratar todas as aplicações igualmente, as redes MPLS podem permitir que as organizações priorizem algumas aplicações de dados sobre outras. Com o MPLS, aplicações em tempo real, como transações com cartão de crédito ou compartilhamento de tela, podem receber prioridade sobre tipos de tráfego menos sensíveis ao tempo, como email.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Noções básicas sobre os tipos de serviços de rede IP: IP básico e MPLS

O encaminhamento original de pacotes IP operava com o princípio de "melhor esforço". Isso significa que os roteadores que encaminhavam os pacotes IP faziam o melhor que podiam para entregá-los ao destino, mas não ofereciam qualquer garantia de quando ou se eles chegariam ao destino. É assim que serviços de Internet básicos funcionam hoje, incluindo a conexão de sua casa. A ideia era que, se a confiabilidade fosse necessária para uma aplicação específica, ela seria fornecida em um nível mais alto na pilha de protocolos. O mecanismo de entrega confiável é o protocolo TCP (Transmission Control Protocol). O protocolo UDP (User Datagram Protocol), usado para voz e vídeo em tempo real, é um mecanismo de entrega não confiável (ou seja, de "melhor esforço"). 
  
O serviço MPLS (Multi-Protocol Label Switching) foi desenvolvido como um meio para os provedores de serviços de rede oferecerem um serviço IP com garantia de boa execução para evitar atraso, tremulação e perda de pacotes. Para produzir essas garantias de desempenho, o MPLS elimina em partes a imprevisibilidade do IP tradicional. Primeiro, em vez de cada pacote passar de roteador em roteador até seu destino (processo cujo resultado poderia ser cada pacote percorrer um caminho diferente), o MPLS encaminha todos os pacotes por uma conexão de "circuito virtual" com uma rota fixa chamada LSP (Label Switched Path). Se um dos links desse caminho falhar, todos os LSPs que usam esse link são rapidamente desviados para outro caminho.
  
Quando um pacote é enviado pela rede MPLS, o roteador de borda do provedor de serviços de rede acrescenta um cabeçalho adicional ao pacote com um rótulo usado para encaminhá-lo pelo LSP adequado. O rótulo é removido pelo roteador de borda da outra extremidade da rede MPLS.
  
Além de simplificar o processo de encaminhamento, a outra vantagem do MPLS é que o sistema de gerenciamento de rede sabe quais conexões estão sendo transportadas por cada link da rede. Ao controlar a forma como tráfego é encaminhado pela rede, o operador pode garantir a QoS que cada caminho fornecerá. Assim, ao contrário do desempenho baseado no melhor esforço do IP tradicional ou básico, os operadores do MPLS podem fornecer um serviço IP com desempenho previsível. Esse LSP também faz do MPLS inerentemente mais seguro que os serviços de Internet tradicionais. Assim, com um serviço de IP básico, podemos esperar que a rede terá um desempenho bom o suficiente para oferecer uma boa qualidade de voz e usará técnicas como FEC e uma codificação de voz mais resiliente para aumentar as chances. A diferença é quemas, com o MPLS, podemos ter certeza disso.
  
Provedores de MPLS oferecem vários gradientes de classe de serviço e, infelizmente usam termos diferentes para identificá-los. Você terá que trabalhar de perto com seu provedor para garantir que eles entendam as saídas da Calculadora de Largura de Banda do [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e as opções recomendadas para diferentes aplicativos de Cargas de Trabalho em Tempo Real Microsoft 365 ou Office 365 em Tempo Real.
  
## <a name="conclusion"></a>Conclusão

O Skype for Business melhora a forma como as comunicações empresarias são conduzidas. Em vez de ter um telefone conectado a um PBX, um sistema de videoconferência autônomo, uma plataforma separada para emails, um serviço externo para audioconferências e algum veículo para IM e presença, o Skype for Business pode oferecer todos esses recursos em uma única interface de usuário.
  
Oferecer serviços de voz e vídeo em tempo real com nível empresarial de forma consistente exige uma infraestrutura de rede completa capaz de fornecer QoS. Isso inclui serviços de LAN e WAN. A Microsoft fornece ferramentas como a [Calculadora de largura de banda do Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) para estimar a capacidade de rede necessária para os vários serviços. Além disso, há parceiros no programa ferramentas de ti Pro soluções: ferramentas de ti Pro que oferecem ferramentas para avaliar [previamente a](https://go.microsoft.com/fwlink/?LinkID=690307) infraestrutura de rede e dar suporte Skype for Business ao monitoramento, ao relatório e à solução de problemas. Sem uma infraestrutura de rede corretamente dimensionada e configurada, você corre o risco de ter uma implantação do Skype for Business ExpressRoute que não atende às expectativas do usuário em relação a qualidade e consistência.
  
Ferramentas empresariais eficazes devem ter um desempenho confiável, consistente e fornecer uma experiência de usuário que incentiva a adoção. De um ponto de vista da rede, isso significa dispor de uma infraestrutura de rede, tanto local quanto para uma área maior, fixa e móvel, que pode permitir que isso aconteça. Planejar, projetar, implantar e manter essa infraestrutura nem sempre é uma tarefa fácil. O hardware, as ferramentas e os serviços de rede para alcançar esse objetivo estão disponíveis hoje em dia, mas é responsabilidade do profissional de TI perceber que eles são criados, implantados e mantidos de forma a garantir que os usuários recebam um conjunto de serviços de comunicação e colaboração que permitirá que eles possam trabalhar com eficiência e eficácia, e que a organização poderá aproveitar ao máximo o que essa tecnologia tem a oferecer. 
  
## <a name="related-topics"></a>Tópicos relacionados

[Documentação do ExpressRoute](/azure/expressroute/)

  
