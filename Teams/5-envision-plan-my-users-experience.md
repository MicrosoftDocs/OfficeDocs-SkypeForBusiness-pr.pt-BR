---
title: Planejar a experiência dos usuários do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Escolha aplicativos cliente do Teams, plano para a qualidade do ponto de extremidade, Obtenha recomendações para a implantação de pontos de extremidade Wi-Fi e escolha dispositivos de áudio.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77a325fbe8cacb3b2760f5b3034dee0e16695278
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021592"
---
# <a name="plan-my-users-experience"></a>Planejar a experiência de meus usuários

Este artigo fornece uma visão geral dos requisitos para identificar corretamente os elementos de sua implantação de serviços de voz em nuvem que afetam diretamente a experiência dos usuários. Ao preparar-se para esses itens antes da implantação, você aumentará as chances de fornecer com êxito uma experiência de alta qualidade e confiabilidade para os usuários. 

## <a name="client-deployment"></a>Implantação do cliente

O Microsoft Teams tem clientes disponíveis para Web, área de trabalho (Windows e Mac) e móvel (Android e iOS). Para obter detalhes adicionais sobre como a área de trabalho (Windows e Mac) e os clientes móveis estão instalados, consulte [obter clientes para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Atualizações de cliente

Um dos principais benefícios do teams é que o cliente é mantido atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planejar a qualidade dos pontos de extremidade

Como você pode ver no diagrama abaixo, os pontos de extremidade são um bloco de construção importante para oferecer uma experiência de qualidade para os usuários.

![Diagrama descrevendo os três componentes de qualidade](media/plan-my-users-experience-image1.png "Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviços se sobrepõe a todos os três componentes. Com foco em pontos de extremidade.")

Os pontos de extremidade do teams podem ser executados em muitos dispositivos, incluindo PCs, Macs, tablets e dispositivos móveis. Parte da experiência não só inclui o dispositivo, mas como um usuário se conecta ao dispositivo — por exemplo, usando o microfone/alto-falante interno do dispositivo, o fones ou um fone de ouvido com microfone otimizado. O uso de um fone de ouvido com microfone otimizado pode melhorar a experiência geral do usuário.

As orientações de planejamento de pontos de extremidade a seguir ajudarão a garantir que sua organização tenha uma experiência de integração com o Microsoft Teams positiva.

## <a name="endpoint-capability"></a>Funcionalidades dos pontos de extremidade

A primeira parte do planejamento é garantir que todos os computadores e outros dispositivos em sua organização possam executar o Teams. Além de examinar os requisitos de hardware, isso também envolve a compreensão das outras atividades do computador em segundo plano. Muitas organizações executam outros softwares, incluindo sistemas de detecção de intrusões e software antimalware, o que pode afetar o desempenho básico de um dispositivo.

Para obter informações sobre os requisitos de software para os clientes do teams em cada plataforma (Web, desktop e dispositivos móveis), consulte [obter clientes para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Os firewalls do lado do cliente podem afetar a qualidade das chamadas, além de impedir o estabelecimento da chamada. Configure as exclusões apropriadas no firewall do cliente de acordo com as informações contidas em [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips). O fornecedor terceirizado deve ter orientações específicas sobre como criar exclusões.

>[!NOTE]
> O Microsoft Teams atualizará automaticamente o Firewall do Windows com uma configuração de firewall apropriada.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendações de Wi-Fi para pontos de extremidade

Isso leva um planejamento significativo para implantar uma rede Wi-Fi otimizada para dar suporte a cargas de trabalho em tempo real no Microsoft Teams. As seções a seguir fornecem algumas orientações gerais que podem ajudar você a evitar armadilhas comuns durante o planejamento de pontos de extremidade.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Alguns drivers de Wi-Fi podem ser problemáticos. Como exemplo, um driver pode ter comportamentos de roaming muito agressivos entre os pontos de acesso, resultando na baixa qualidade das chamadas.
Isso não é uma ocorrência comum, mas é importante garantir que os drivers de Wi-Fi no computador tenham sido atualizados e testados antes da implantação.

### <a name="wi-fi-bands"></a>Bandas de Wi-Fi

Existem dois tipos de bandas principais usadas atualmente nos equipamentos de Wi-Fi: 2,4 GHz e 5,0 GHz. Se a sua organização oferece as duas bandas, você deve configurar o driver para preferir a banda de 5,0 GHz. Essa banda é muito mais densa em termos de taxa de transferência, sendo menos afetada pela interferência observada na banda de 2,4 GHz.
Essa recomendação presume que você tenha otimizado a banda de 5,0 GHz corretamente.

### <a name="wi-fi-radio-type"></a>Tipo de rádio de Wi-Fi

Planeje usar dispositivos que dão suporte aos tipos de rádio de Wi-Fi mais novos. Você poderá obter excelente desempenho do Wi-Fi se utilizar o tipo 802.11ac ou mais recente nos dispositivos provisionados.

### <a name="wireless-avoidance"></a>Rejeição de redes sem fio

Algumas organizações preferem evitar totalmente as redes Wi-Fi. Às vezes, essas orientação é fornecida por meio de uma recomendação de que os usuários se conectem diretamente a uma rede com fio. Em alguns casos, a ordem de associação de redes pode ter a conexão sem fio como preferencial e continuar usando essa conexão, mesmo que o computador esteja conectado à rede com fio. Para evitar esse comportamento indesejado, configure a ordem de associação de modo a evitar esse cenário.

### <a name="80211-power-save-protocol"></a>Protocolo de economia de energia do 802,11

Se a sua organização usa pontos de acesso sem fio ou roteadores que não dão suporte ao protocolo de economia de energia do 802,11, você pode ter chamadas descartadas ou baixa qualidade de chamada no Microsoft Teams em execução em dispositivos Windows. Se não for possível atualizar seus pontos de acesso ou roteadores sem fio, atualize as configurações do Plano de Energia do Windows dos dispositivos que funcionam com energia da bateria. Outros detalhes e orientações de configuração estão disponíveis neste [artigo de suporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Quais clientes do teams serão implantados em sua organização?</li><li>Como você implementará inicialmente os clientes do teams para seus usuários?</li><li>Quem é responsável pela avaliação de pontos de extremidade e dispositivos para validá-los que atendem aos requisitos do teams para obter uma experiência de qualidade?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Documentar o processo que será seguido para implantar clientes do teams.</li><li>Avalie pontos de extremidade e dispositivos e execute e remediação necessários.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos para o Microsoft Teams

O Microsoft Teams pode ser usado para reuniões ou como um sistema de telefonia. Ao usar esses recursos, o dispositivo de interface que é usado para o Microsoft Teams tem um papel importante na experiência do usuário.

O uso do viva-voz e do microfone internos do computador pode ser aceitável para os usuários que têm essa configuração. Mas geralmente, esses dispositivos não são otimizados para cancelamento de ruído, e qualquer tipo de ruído ambiental pode ter um impacto downstream em outras pessoas na chamada. A utilização de dispositivos otimizados para esses cenários ajuda a garantira uma experiência de alta qualidade.

Cada dispositivo precisa atender às necessidades de seus usuários. Você precisará adaptar os dispositivos, como fones de ouvido com microfone, para as diferentes personas e os diferentes casos de uso em sua organização.
Um exercício de mapeamento entre personas e dispositivos deve ser realizado como parte do processo de planejamento.

Depois de selecionar os dispositivos, inclua-os no plano de testes do piloto para a validação final. Faça pesquisas durante o piloto para obter comentários e assim garantir que sua estratégia de dispositivos seja a ideal.

> [!NOTE]
> No momento, recomendamos usar dispositivos de áudio certificados pelo Programa de Certificação do Skype for Business. Para localizar dispositivos certificados neste programa, consulte dispositivos e dispositivos de áudio e [vídeo USB](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)do [Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices) .



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decidir sobre a estratégia geral de dispositivos da sua organização para experiências de usuário e de sala de reunião.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Concluir um exercício de mapeamento de um ponto a dispositivo para sua organização.</li><li>Documentar o processo de obtenção de dispositivos para usuários e salas de reunião.</li><li>Documentar o processo de implantação e configuração de dispositivos para usuários e salas de reunião.</li><li>Adquirir dispositivos iniciais para começar sua implantação.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
