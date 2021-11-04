---
title: Planejar o bypass de mídia Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Decisões necessárias para o planejamento de bypass de mídia Skype for Business Server Enterprise Voice. Inclui a interoperação com o controle de admissão de chamada (CAC).
ms.openlocfilehash: ef06cd7e97623024ab921bf71a006645d1d97a07
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759523"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planejar o bypass de mídia Skype for Business

Decisões necessárias para o planejamento de bypass de mídia Skype for Business Server Enterprise Voice. Inclui a interoperação com o controle de admissão de chamada (CAC).

Desvio de mídia refere-se à remoção do Servidor de Mediação do caminho da mídia, sempre que possível para chamadas cuja sinalização percorre o Servidor de Mediação.

O desvio de mídia pode aprimorar a qualidade da voz reduzindo latência, conversões desnecessárias, possibilidade de perda de pacotes e o número de pontos de falha possíveis. A escalabilidade pode ser aprimorada, porque a eliminação do processamento de mídia para chamadas desviadas reduz a carga no Servidor de Mediação. Essa redução de carga complementa a capacidade do Servidor de Mediação de controlar vários gateways.

 Em que um site de filial sem um Servidor de Mediação está conectado a um site central por um ou mais links wan com largura de banda restrita, o desvio de mídia reduz o requisito de largura de banda permitindo que a mídia de um cliente em um site de filial flua diretamente para seu gateway local sem primeiro ter que fluir através do link WAN para um Servidor de Mediação no site central e voltar.

Ao aliviar o Servidor de Mediação do processamento de mídia, o bypass de mídia também pode reduzir o número de Servidores de Mediação que uma infraestrutura Enterprise Voice requer. Como regra geral, habilite o desvio de mídia onde possível.

A figura a seguir exibe caminhos de mídia e sinalização básicos em topologias com e sem desvio de mídia.

**Caminhos de mídia e sinalização com e sem desvio de mídia**

![Voice CAC Media Bypass Connection Enforcement.](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

O bypass de mídia é útil quando você deseja minimizar o número de Servidores de Mediação implantados. Geralmente, um pool de Servidores de Mediação será implantado em um site central e controlará os gateways em sites locais. Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites. Skype for Business Server de chamadas de saída e Enterprise Voice políticas devem ser configuradas corretamente para que as chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.

As redes Wi-Fi geralmente enfrentam uma maior perda de pacotes do que as redes com fio. A recuperação desta perda de pacotes não é algo que geralmente possa ser acomodado por gateways. Assim, recomendamos a avaliação da qualidade da rede Wi-Fi antes de determinar se o bypass deve estar habilitado para uma sub-rede sem fio. Há uma compensação na redução da latência contra a recuperação da perda de pacotes a considerar. RTAudio, um codec disponível para chamadas que não ignorem o Servidor de Mediação, é mais adequado para tratar da perda de pacotes.

## <a name="planning-your-media-bypass-deployment"></a>Planejando sua implantação de bypass de mídia

Após a estrutura do seu Enterprise Voice estiver inserida, o planejamento do bypass de mídia é aberto.

- Se você possui uma topologia centralizada sem links WAN para sites de filiais, é possível habilitar o bypass de mídia global, pois é necessário um ajuste refinado.

- Se você não possui uma topologia distribuída que consiste de uma ou mais regiões de rede e seus sites de filiais associados, determine o seguinte:

  - Se os seus colegas do Servidor de Mediação podem suportar as capacidades necessárias para bypass de mídia.

  - Quais sites em cada região de rede estão bem conectados.

  - Qual combinação de bypass de mídia e controle de admissão de chamada é adequada para sua rede.

Quando o desvio de mídia é habilitado, um ID de desvio exclusivo é gerado automaticamente para uma região de rede e para todos os sites de rede sem limites de largura de banda nessa região. Os sites com limites de largura de banda na região e os sites conectados à região por links WAN com limites de largura de banda obtêm seus próprios IDs de desvio exclusivos.

Quando um usuário faz uma chamada para o PSTN, o Servidor de Mediação compara a ID de bypass da sub-rede do cliente com a ID de bypass da sub-rede do gateway. Se os dois IDs de desvio forem correspondentes, o desvio de mídia será usado para a chamada. Se as IDs de bypass não corresponderem, a mídia da chamada deverá fluir pelo Servidor de Mediação.

Quando um usuário recebe uma chamada da PSTN, o cliente do usuário compara sua ID de bypass com a do gateway PSTN. Se as duas IDs de bypass corresponderem, a mídia fluirá diretamente do gateway para o cliente, ignorando o Servidor de Mediação.

Somente os clientes e dispositivos mais novos do Lync 2010 suportam interações de bypass de mídia com um Servidor de Mediação.

> [!IMPORTANT]
> Além de habilitar o bypass de mídia globalmente, é necessário habilitar o bypass de mídia individualmente em cada tronco PSTN. Se o bypass estiver habilitado globalmente, mas não estiver habilitado para um determinado tronco PSTN, o bypass de mídia não será invocado para qualquer chamada envolvendo aquele tronco PSTN. Além disso, quando o bypass de mídia é definido para **Usar a informação do site e da região**, é necessário associar todas as sub-redes roteáveis com os sites nos quais estão localizadas. Se há sub-redes roteáveis dentro de um site no qual o bypass não é desejado, estas sub-redes devem ser agrupadas dentro de um novo site antes de habilitar o bypass de mídia. Fazer isso garantirá que as sub-redes não roteáveis sejam atribuídas com uma ID de bypass diferente.


## <a name="media-bypass-modes"></a>Modos de bypass de mídia

Configure o desvio de mídia globalmente e para cada tronco PSTN individual. Ao habilitar o desvio de mídia globalmente, você tem duas opções: **Sempre Ignorar** e **Usar Informações de Local e Região**.

Como o nome sugere, **Sempre Desviar** significa que o desvio será tentado para todas as chamadas de PSTN. **Sempre Desviar** é usado para as implantações em que não há necessidade de ativar o controle de admissão da chamada, e nem de especificar informações detalhadas da configuração de quando tentar o desvio de mídia. Além disso, **Sempre Desviar** é usado quando existe uma conectividade total entre os clientes e os gateways de PSTN. Nesta configuração, todas as sub-redes são mapeadas apenas para um ID de desvio, que é calculado pelo sistema.

Quando **Usar Informações do Local e Região**, o ID do desvio é associado à configuração do local e de região usada para tomar a decisão do desvio. Essa configuração fornece a flexibilidade de configurar o desvio para as topologias mais comuns, porque permite um controle refinado de quando o desvio acontece, além de suportar as interações com o controle de admissão de chamadas (CAC). O sistema tentar aliviar sua tarefa, atribuindo automaticamente os IDs de desvio conforme segue.

- O sistema atribui automaticamente um único ID de desvio exclusivo para cada região.

- Qualquer local conectado a uma região via link WAN, sem restrições de largura de banda, herda o mesmo ID de desvio que a região.

- Um local associado à região via link WAN com largura de banda restrita é atribuído a um ID de desvio diferente do da região.

- As sub-redes associadas a cada site herdam o ID de desvio do site.

## <a name="media-bypass-and-call-admission-control"></a>Bypass de mídia e controle de admissão de chamada

O desvio de mídia e o controle de admissão de chamadas trabalham juntos para gerenciar o controle de largura de banda da mídia de chamadas. O desvio de mídia facilita o fluxo da mídia por links bem conectados, enquanto o controle de admissão de chamadas gerencia o tráfego nos links com limites de largura de banda. Como o Desvio de Mídia e o controle de admissão de chamadas são mutuamente exclusivos, você deve estar atento a um quando estiver planejando o outro. Há suporte para as seguintes combinações:

- CAC e Desvio de Mídia estão habilitados. O Desvio de Mídia deve estar definido como **Usar informações de site e da região**. As informações do site e da região são as mesmas usadas para o CAC.

    Se você habilitar o CAC, não poderá selecionar **Sempre Ignorar** e vice-versa, pois as duas configurações são mutuamente exclusivas. Ou seja, apenas um dos dois se aplicará a qualquer chamada PSTN determinada. Primeiro, uma verificação é feita para determinar se o bypass de mídia se aplica à chamada. Se isso acontecer, o CAC não será usado. Isso faz sentido, porque se uma chamada for qualificada para bypass, ela será por definição usando uma conexão em que o CAC não é necessário. Se o bypass não puder ser aplicado à chamada (ou seja, se as IDs de bypass do cliente e do gateway não corresponderem), o CAC será aplicado à chamada.

- CAC não habilitado e Desvio de Mídia definido como **Desviar Sempre**.

    Nesta configuração, as sub-redes do cliente e do tronco são mapeadas a um único ID de desvio, que é computado pelo sistema.

- CAC não habilitado e Desvio de Mídia definido é definido como **Usar Informações do Site e da Região**.

    Onde **Usar Informações do Site e da Região** estiver disponível, a determinação do desvio funciona essencialmente da mesma maneira, independente de o CAC estar habilitado ou não. Ou seja, para qualquer chamada PSTN determinada, a sub-rede do cliente é mapeada para um site específico e a ID de bypass dessa sub-rede é extraída. Da mesma forma, a sub-rede do gateway é mapeada para um site específico e a ID de bypass dessa sub-rede é extraída. Somente se duas IDs de desvio forem idênticas o desvio acontecerá para a chamada. Caso não sejam idênticas, o desvio de chamada não irá acontecer.

    Ainda que o CAC esteja desabilitado globalmente, a política de largura de banda precisa ser definida para cada site e link se você quiser usar a configuração site-e-região para controlar a decisão de desvio. O valor real da restrição de largura de banda ou sua modalidade não importa. O objetivo final é que o sistema calcule automaticamente as IDs diferentes de desvio para associar aos locais diferentes que não estão bem conectados. Definir a restrição da largura de banda por definição significa que um link não está bem conectado.

- O CAC está habilitado, mas o desvio de mídia não. Isso se aplica apenas onde todos os gateways e IP-PBXs não estão bem conectados ou não atendem outros requisitos para desvio de mídia. Para obter detalhes sobre requisitos de desvio de mídia, consulte [Requirements for Media Bypass](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-media-bypass).

## <a name="technical-requirements"></a>Requisitos técnicos

Para cada chamada para o PSTN, o Servidor de Mediação determina se a mídia do ponto de extremidade Skype for Business de origem pode ser enviada diretamente para um par do Servidor de Mediação sem atravessar o Servidor de Mediação. O par pode ser um gateway PSTN, um IP-PBX ou um SBC (Controlador de Borda de Sessão) em um ITSP (provedor de serviços de telefonia da Internet) associado ao tronco entre o Servidor de Mediação para o qual a chamada é encaminhada.

O desvio de mídia pode ser empregado quando os seguintes requisitos são atendidos:

- Um par do Servidor de Mediação deve dar suporte aos recursos necessários para o bypass de mídia, o mais importante é a capacidade de lidar com várias respostas bifurcadas (conhecidas como "caixas de diálogo in-loco"). Contate o fabricante do seu gateway ou PBX ou seu ITSP para obter o valor do número máximo de caixas de diálogo iniciais que o gateway, o PBX ou o SBC pode aceitar.

- O par do Servidor de Mediação deve aceitar o tráfego de mídia diretamente Skype for Business pontos de extremidade. Muitos ITSPs permitem que seu SBC receba tráfego apenas do Servidor de Mediação. Entre em contato com o ITSP para determinar se o SBC aceita o tráfego de mídia diretamente Skype for Business pontos de extremidade.

- Skype for Business clientes e um par do Servidor de Mediação devem estar bem conectados, o que significa que eles estão localizados na mesma região de rede ou em sites de rede que se conectam à região por meio de links WAN que não têm restrições de largura de banda