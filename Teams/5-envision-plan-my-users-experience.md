---
title: Planejar a experiência dos usuários do Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Escolha a aplicativos de cliente de equipes, planejar a qualidade do ponto de extremidade, obtém recomendações para a implantação de pontos de extremidade Wi-Fi e escolhendo dispositivos de áudio.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 866395a4dd58016c0989ec4b34f602877251d021
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="plan-my-users-experience"></a>Planejar a experiência dos meus usuários

Este artigo fornece uma visão geral dos requisitos de adequadamente que identifica os elementos da sua implantação de serviços de voz de nuvem que afetam diretamente a experiência dos usuários. Ao preparar-se para esses itens antes da implantação, você vai aumentar as chances de fornecimento com êxito uma experiência de alta qualidade e confiável para os usuários. 

## <a name="client-deployment"></a>Implantação do cliente

O Microsoft Teams tem clientes disponíveis para web, desktop (Windows e Mac) e móvel (Android, iOS e Windows Phone). Para obter detalhes adicionais sobre como os clientes móveis e área de trabalho (Windows e Mac) são instalados, consulte [obter clientes para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Atualizações do cliente

Um dos principais benefícios de equipes é que o cliente sejam mantido atualizado automaticamente. Os clientes no PC e Mac são atualizados usando um processo de plano de fundo que verifica se há novas compilações e baixa o novo cliente quando o aplicativo estiver ocioso.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planejar a qualidade do ponto de extremidade

Como você pode ver do diagrama a seguir, os pontos de extremidade são um bloco de construção importante no fornecimento de uma experiência de qualidade para usuários.

![Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco nos pontos de extremidade.] (media/plan-my-users-experience-image1.png "Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco nos pontos de extremidade.")

Pontos de extremidade de equipes podem ser executado em vários dispositivos, incluindo PCs, Macs, tablets e dispositivos móveis. Parte da experiência abrange não apenas o dispositivo, mas como um usuário se conecta ao dispositivo — por exemplo, usando microfone/alto-falante interno do dispositivo, fones de ouvido com ou um headset otimizada. Usar um fone de ouvido otimizada pode enriquecer a experiência geral do usuário.

A orientação sobre o planejamento de ponto de extremidade a seguir ajudarão você a Certifique-se de que sua organização tem uma inclusão bem-sucedida de experiência com equipes.

## <a name="endpoint-capability"></a>Recurso de ponto de extremidade

A primeira parte do planejamento é garantir que todos os PCs e outros dispositivos em sua organização podem executar as equipes. Isso envolve não só olhando os requisitos de hardware, mas também Noções básicas sobre o que mais PC está fazendo em segundo plano. Muitas organizações executarem outros softwares, incluindo os sistemas de detecção de invasão e software de antimalware, que pode afetar o desempenho de base de um dispositivo.

Para obter informações sobre os requisitos de software para as equipes de clientes em cada plataforma (web, desktop e portáteis), consulte [obter clientes para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Firewalls do ponto de extremidade

Firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Firewalls do lado do cliente podem afetar a qualidade da chamada além impedindo uma chamada de sendo estabelecida. Configure as exclusões apropriadas no firewall cliente com base nas informações em [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips). O fornecedor terceirizado terão orientações específicas sobre como criar as exclusões.

>[!NOTE]
> Microsoft Teams atualizará automaticamente o Firewall do Windows com uma configuração de firewall apropriada.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendações de Wi-Fi para pontos de extremidade

Leva significativo planejando implantar uma rede Wi-Fi otimizada para suportar cargas de trabalho em tempo real no Microsoft Teams. As seções a seguir fornecem algumas diretrizes gerais que podem ajudá-lo a evitar armadilhas comuns durante o planejamento para os pontos de extremidade.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Alguns drivers Wi-Fi podem ser problemáticos. Por exemplo, um driver pode ter muito agressivos comportamentos roaming entre os pontos de acesso, causando a qualidade de chamadas ruins.
Isso não é uma ocorrência comum, mas é importante garantir que os drivers de Wi-Fi no PC foram atualizados e testados antes da implantação.

### <a name="wi-fi-bands"></a>Faixas Wi-Fi

Existem basicamente dois tipos de faixas usados em equipamento hoje Wi-Fi, 2,4 GHz e GHz 5.0. Se sua organização fornece as duas faixas, você deve configurar as configurações do driver para preferir faixa de GHz 5.0. Este banda é muito mais densos em termos de taxa de transferência e menor afetado por essa interferência Vista na faixa de 2,4 GHz.
Essa recomendação pressupõe que você tiver otimizado adequadamente banda de rede de GHz 5.0.

### <a name="wi-fi-radio-type"></a>Tipo de rádio Wi-Fi

Plano para dispositivos que oferecem suporte os tipos de rádio Wi-Fi mais recentes. Você pode obter um desempenho muito bom Wi-Fi, se você aproveitar a 802.11ac ou mais recente nos dispositivos de provisionar.

### <a name="wireless-avoidance"></a>Contenção de sem fio

Algumas organizações preferem evitar Wi-Fi totalmente. Em alguns casos, este guia é fornecido por meio de uma recomendação para os usuários se conectarem diretamente a uma rede com fio. Em alguns casos, a ordem de ligação de rede pode ter a conexão sem fio preferencial e continuar a usar essa conexão, mesmo que o PC esteja conectado para a conexão com fio. Para evitar esse comportamento acidentais, configure a ordem de ligação para evitar esse cenário.

### <a name="80211-power-save-protocol"></a>802.11 protocolo de economia de energia

Se sua organização usa pontos de acesso sem fio ou roteadores que não há suporte para o protocolo de economia de energia 802.11, você pode sofrer capitular chamadas ou a qualidade de chamadas ruins em Teams da Microsoft em execução em dispositivos do Windows. Se não for possível atualizar o ponto de acesso sem fio ou roteadores, você deverá atualizar as configurações de plano de energia do Windows em dispositivos que executam com bateria. Diretrizes de configuração e os detalhes mais são fornecidas no seguinte [artigo de suporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Quais clientes equipes serão implantados em sua organização?</li><li>Como você inicialmente implantará clientes de equipes para seus usuários?</li><li>Eles quem é responsável por avaliar os pontos de extremidade e dispositivos para validar atende aos requisitos de equipes para uma experiência de qualidade?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>O processo que será seguido para implantar clientes de equipes do documento.</li><li>Avalie os pontos de extremidade e dispositivos e executar e remediação necessária.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos para equipes

Microsoft Teams pode ser usadas para reuniões ou como um sistema telefônico. Ao usar esses recursos, o dispositivo de interface que é usado para equipes desempenha um papel importante na experiência do usuário.

Usando um alto-falante e microfone de internas pode parecer aceitável ao usuário que tem essa configuração. Normalmente, mas esses dispositivos não otimizados para o cancelamento de ruído e qualquer tipo de ruído ambiental pode ter um impacto downstream em outros na chamada. Aproveitando a dispositivos otimizados para esses cenários ajudará a garantir uma experiência de alta qualidade.

Cada dispositivo deve atender às necessidades dos seus usuários. Você precisará ajustar os dispositivos como fones de ouvido para os diferentes personagens e casos de uso em sua organização.
Um exercício de mapeamento de pessoa para dispositivo deve ser concluído como parte do processo de planejamento.

Depois que você selecionou os dispositivos, incluí-los no plano de teste piloto para validação final. Pesquisas de alavancar durante o piloto para coletar comentários para garantir que sua estratégia de dispositivo é ideal.

> [!NOTE]
> Neste momento, recomendamos o uso de dispositivos de áudio que foram certificados por meio do Skype para o programa de certificação de negócios. Para localizar dispositivos certificados sob este programa, consulte o catálogo de soluções [USB dispositivos Certified para Skype para negócios](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida qual estratégia de dispositivo geral da sua organização para o usuário e experiências de sala de reunião.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Conclua um exercício de mapeamento do dispositivo de pessoa para a sua organização.</li><li>O processo para obtenção de dispositivos para usuários e salas de reunião do documento.</li><li>O processo de implantação e configuração de dispositivos para usuários e salas de reunião do documento.</li><li>Adquirir dispositivos iniciais para começar sua implantação.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->