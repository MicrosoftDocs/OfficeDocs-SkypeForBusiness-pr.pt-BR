---
title: Planejar a experiência dos usuários do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Escolha a aplicativos de cliente de equipes, planejar a qualidade do ponto de extremidade, obtém recomendações para a implantação de pontos de extremidade Wi-Fi e escolhendo dispositivos de áudio.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c36855f4283e9cb57ef2ce0f916899232222777f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241619"
---
# <a name="plan-my-users-experience"></a>Planejar a experiência dos meus usuários

Este artigo fornece uma visão geral dos requisitos de adequadamente que identifica os elementos da sua implantação de serviços de voz de nuvem que afetam diretamente a experiência dos usuários. Ao preparar-se para esses itens antes da implantação, você vai aumentar as chances de fornecimento com êxito uma experiência de alta qualidade e confiável para os usuários. 

## <a name="client-deployment"></a>Implantação do cliente

Microsoft Teams tem clientes disponíveis para a área de trabalho, web (Windows e Mac) e mobile (Android e iOS). Para obter detalhes adicionais sobre como os clientes móveis e área de trabalho (Windows e Mac) são instalados, consulte [obter clientes para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Atualizações de cliente

Um dos principais benefícios de equipes é que o cliente sejam mantido atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planejar a qualidade dos pontos de extremidade

Como você pode ver do diagrama a seguir, os pontos de extremidade são um bloco de construção importante no fornecimento de uma experiência de qualidade para usuários.

![Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco nos pontos de extremidade.] (media/plan-my-users-experience-image1.png "Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco nos pontos de extremidade.")

Pontos de extremidade de equipes podem ser executado em vários dispositivos, incluindo PCs, Macs, tablets e dispositivos móveis. Parte da experiência abrange não apenas o dispositivo, mas como um usuário se conecta ao dispositivo — por exemplo, usando microfone/alto-falante interno do dispositivo, fones de ouvido com ou um headset otimizada. O uso de um fone de ouvido com microfone otimizado pode melhorar a experiência geral do usuário.

As orientações de planejamento de pontos de extremidade a seguir ajudarão a garantir que sua organização tenha uma experiência de integração com o Microsoft Teams positiva.

## <a name="endpoint-capability"></a>Funcionalidades dos pontos de extremidade

A primeira parte do planejamento é garantir que todos os PCs e outros dispositivos em sua organização podem executar as equipes. Além de examinar os requisitos de hardware, isso também envolve a compreensão das outras atividades do computador em segundo plano. Muitas organizações executam outros softwares, incluindo sistemas de detecção de intrusões e software antimalware, o que pode afetar o desempenho básico de um dispositivo.

Para obter informações sobre os requisitos de software para as equipes de clientes em cada plataforma (web, desktop e portáteis), consulte [obter clientes para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Os firewalls do lado do cliente podem afetar a qualidade das chamadas, além de impedir o estabelecimento da chamada. Configure as exclusões apropriadas no firewall do cliente de acordo com as informações contidas em [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips). O fornecedor terceirizado deve ter orientações específicas sobre como criar exclusões.

>[!NOTE]
> O Microsoft Teams atualizará automaticamente o Firewall do Windows com uma configuração de firewall apropriada.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendações de Wi-Fi para pontos de extremidade

Leva significativo planejando implantar uma rede Wi-Fi otimizada para suportar cargas de trabalho em tempo real no Microsoft Teams. As seções a seguir fornecem algumas diretrizes gerais que podem ajudá-lo a evitar armadilhas comuns durante o planejamento para os pontos de extremidade.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Alguns drivers Wi-Fi podem ser problemáticos. Como exemplo, um driver pode ter comportamentos de roaming muito agressivos entre os pontos de acesso, resultando na baixa qualidade das chamadas.
Isso não é uma ocorrência comum, mas é importante garantir que os drivers de Wi-Fi no PC foram atualizados e testados antes da implantação.

### <a name="wi-fi-bands"></a>Bandas de Wi-Fi

Existem dois tipos de bandas principais usadas atualmente nos equipamentos de Wi-Fi: 2,4 GHz e 5,0 GHz. Se a sua organização oferece as duas bandas, você deve configurar o driver para preferir a banda de 5,0 GHz. Essa banda é muito mais densa em termos de taxa de transferência, sendo menos afetada pela interferência observada na banda de 2,4 GHz.
Essa recomendação presume que você tenha otimizado a banda de 5,0 GHz corretamente.

### <a name="wi-fi-radio-type"></a>Tipo de rádio de Wi-Fi

Planeje usar dispositivos que dão suporte aos tipos de rádio de Wi-Fi mais novos. Você poderá obter excelente desempenho do Wi-Fi se utilizar o tipo 802.11ac ou mais recente nos dispositivos provisionados.

### <a name="wireless-avoidance"></a>Rejeição de redes sem fio

Algumas organizações preferem evitar totalmente as redes Wi-Fi. Às vezes, essas orientação é fornecida por meio de uma recomendação de que os usuários se conectem diretamente a uma rede com fio. Em alguns casos, a ordem de associação de redes pode ter a conexão sem fio como preferencial e continuar usando essa conexão, mesmo que o computador esteja conectado à rede com fio. Para evitar esse comportamento indesejado, configure a ordem de associação de modo a evitar esse cenário.

### <a name="80211-power-save-protocol"></a>802.11 protocolo de economia de energia

Se sua organização usa pontos de acesso sem fio ou roteadores que não há suporte para o protocolo de economia de energia 802.11, você pode sofrer capitular chamadas ou a qualidade de chamadas ruins em Teams da Microsoft em execução em dispositivos do Windows. Se não for possível atualizar seus pontos de acesso ou roteadores sem fio, atualize as configurações do Plano de Energia do Windows dos dispositivos que funcionam com energia da bateria. Outros detalhes e orientações de configuração estão disponíveis neste [artigo de suporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Quais clientes equipes serão implantados em sua organização?</li><li>Como você inicialmente implantará clientes de equipes para seus usuários?</li><li>Eles quem é responsável por avaliar os pontos de extremidade e dispositivos para validar atende aos requisitos de equipes para uma experiência de qualidade?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>O processo que será seguido para implantar clientes de equipes do documento.</li><li>Avalie os pontos de extremidade e dispositivos e executar e remediação necessária.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos para o Microsoft Teams

O Microsoft Teams pode ser usado para reuniões ou como um sistema de telefonia. Ao usar esses recursos, o dispositivo de interface que é usado para o Microsoft Teams tem um papel importante na experiência do usuário.

O uso do viva-voz e do microfone internos do computador pode ser aceitável para os usuários que têm essa configuração. Normalmente, mas esses dispositivos não otimizados para o cancelamento de ruído e qualquer tipo de ruído ambiental pode ter um impacto downstream em outros na chamada. A utilização de dispositivos otimizados para esses cenários ajuda a garantira uma experiência de alta qualidade.

Cada dispositivo precisa atender às necessidades de seus usuários. Você precisará adaptar os dispositivos, como fones de ouvido com microfone, para as diferentes personas e os diferentes casos de uso em sua organização.
Um exercício de mapeamento entre personas e dispositivos deve ser realizado como parte do processo de planejamento.

Depois de selecionar os dispositivos, inclua-os no plano de testes do piloto para a validação final. Faça pesquisas durante o piloto para obter comentários e assim garantir que sua estratégia de dispositivos seja a ideal.

> [!NOTE]
> No momento, recomendamos usar dispositivos de áudio certificados pelo Programa de Certificação do Skype for Business. Para localizar dispositivos certificados sob este programa, consulte o catálogo de soluções [USB dispositivos Certified para Skype para negócios](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida qual estratégia de dispositivo geral da sua organização para o usuário e experiências de sala de reunião.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Conclua um exercício de mapeamento do dispositivo de pessoa para a sua organização.</li><li>O processo para obtenção de dispositivos para usuários e salas de reunião do documento.</li><li>O processo de implantação e configuração de dispositivos para usuários e salas de reunião do documento.</li><li>Adquirir dispositivos iniciais para começar sua implantação.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->