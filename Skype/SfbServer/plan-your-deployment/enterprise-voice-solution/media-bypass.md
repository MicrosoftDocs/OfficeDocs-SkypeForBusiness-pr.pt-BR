---
title: Planejar a bypass de mídia no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Decisões necessárias para o planejamento de bypass de mídia no Skype for Business Server Enterprise Voice. Inclui interoperabilidade com o controle de admissão de chamadas (CAC).
ms.openlocfilehash: aed78aa12f593f834bc2c694fec87d5d31e6e47b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802701"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planejar a bypass de mídia no Skype for Business

Decisões necessárias para o planejamento de bypass de mídia no Skype for Business Server Enterprise Voice. Inclui interoperabilidade com o controle de admissão de chamadas (CAC).

O bypass de mídia se refere a remover o servidor de mediação do caminho de mídia sempre que possível para chamadas cujo sinal percorre o servidor de mediação.

O bypass de mídia pode aprimorar a qualidade da voz reduzindo a latência, conversões desnecessárias, possibilidade de perda de pacotes e o número de pontos de falha possíveis. A escalabilidade pode ser aprimorada, pois a eliminação do processamento de mídia para chamadas ignoradas reduz a carga no servidor de mediação. Essa redução na carga complementa a capacidade do servidor de mediação para controlar vários gateways.

 Onde um site de filiais sem um servidor de mediação está conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduz a necessidade de largura de banda ao permitir que a mídia de um cliente em um site de filiais flua diretamente para seu gateway local sem Primeiro, é necessário fluir pelo link de WAN para um servidor de mediação no site central e para trás.

Ao enliberar o servidor de mediação do processamento de mídia, o bypass da mídia também pode reduzir o número de servidores de mediação que uma infraestrutura Enterprise Voice requer. Como regra geral, habilite o bypass de mídia sempre que possível.

A figura a seguir exibe caminhos de mídia e sinalização básicos em topologias com e sem bypass de mídia.

**Caminhos de mídia e sinalização com e sem desvio de mídia**

![Aplicação de voz do CAC ignorando a imposição de conexão](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

O bypass de mídia é útil quando você deseja minimizar o número de servidores de mediação implantados. Geralmente, um pool de servidores de mediação será implantado em um site central, e ele controlará os gateways em sites de filiais. Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites. Os roteiros de chamadas de saída do Skype for Business Server e as políticas de voz corporativa devem ser configurados corretamente para que as chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.

As redes Wi-Fi geralmente enfrentam uma maior perda de pacotes do que as redes com fio. A recuperação desta perda de pacotes não é algo que geralmente possa ser acomodado por gateways. Assim, recomendamos a avaliação da qualidade da rede Wi-Fi antes de determinar se o bypass deve estar habilitado para uma sub-rede sem fio. Há uma compensação na redução da latência contra a recuperação da perda de pacotes a considerar. RTAudio, um codec disponível para chamadas que não ignorem o Servidor de Mediação, é mais adequado para tratar da perda de pacotes.

## <a name="planning-your-media-bypass-deployment"></a>Planejando a implantação do bypass de mídia

Depois que a estrutura da sua empresa estiver no lugar certo, é simples planejar o bypass de mídia.

- Se você possui uma topologia centralizada sem links WAN para sites de filiais, é possível habilitar o bypass de mídia global, pois é necessário um ajuste refinado.

- Se você não tem uma topologia distribuída que consiste em uma ou mais regiões de rede e seus sites de filiais associados, determine o seguinte:

  - Se os seus colegas do Servidor de Mediação oferecem suporte aos recursos necessários para o bypass de mídia.

  - Quais sites em cada região de rede estão bem conectados.

  - Qual combinação de bypass de mídia e controle de admissão de chamada é adequada para sua rede.

Quando o bypass de mídia é habilitado, uma ID de bypass exclusiva é gerado automaticamente para uma região de rede e para todos os sites de rede sem limites de largura de banda nessa região. Os sites com limites de largura de banda na região e os sites conectados à região por links WAN com limites de largura de banda obtêm suas próprias IDs de bypass exclusivas.

Quando um usuário faz uma chamada para a PSTN, o servidor de mediação compara a ID de bypass da sub-rede do cliente com a ID de bypass da sub-rede do gateway. Se as duas IDs de bypass forem correspondentes, o bypass de mídia será usado na chamada. Se as IDs de bypass não corresponderem, a mídia para a chamada deve fluir pelo servidor de mediação.

Quando um usuário recebe uma chamada da PSTN, o cliente do usuário compara a ID de bypass com a do gateway PSTN. Se as duas IDs de bypass corresponderem, a mídia fluirá diretamente do gateway para o cliente, ignorando o servidor de mediação.

Somente os clientes ou dispositivos do Lync 2010 ou mais recentes dão suporte a interações de bypass de mídia com um servidor de mediação.

> [!IMPORTANT]
> Além de habilitar o bypass de mídia globalmente, é necessário habilitar o bypass de mídia individualmente em cada tronco PSTN. Se o bypass estiver habilitado globalmente, mas não estiver habilitado para um determinado tronco PSTN, o bypass de mídia não será invocado para qualquer chamada envolvendo aquele tronco PSTN. Além disso, quando o bypass de mídia é definido para **Use Site and Region Information** (Usar informações do site e da região) é necessário associar todas as sub-redes roteáveis com os sites nos quais estão localizadas. Se há sub-redes roteáveis dentro de um site no qual o bypass não é desejado, estas sub-redes devem ser agrupadas dentro de um novo site antes de habilitar o bypass de mídia. Fazer isso garantirá que as sub-redes não roteáveis sejam atribuídas com uma ID de bypass diferente.

## <a name="media-bypass-modes"></a>Modos de bypass de mídia

Configure o bypass de mídia globalmente e para cada tronco PSTN individual. Ao habilitar o bypass de mídia globalmente, você tem duas opções: **Sempre ignorar** e **Use Site and Region Information** (Usar informações do site e da região).

Como o nome sugere, **Sempre ignorar** significa que o bypass será tentado para todas as chamadas de PSTN. **Sempre ignorar** é usado para as implantações em que não há necessidade de ativar o controle de admissão da chamada, e nem de especificar informações detalhadas da configuração de quando tentar o bypass de mídia. Além disso, **Sempre ignorar** é usado quando existe uma conectividade total entre os clientes e os gateways de PSTN. Nesta configuração, todas as sub-redes são mapeadas apenas para um ID de bypass, que é calculado pelo sistema.

Com **Use Site and Region Information** (Usar informações do site e da região), a ID de bypass é associada à configuração do site e de região usada para tomar a decisão do bypass. Essa configuração fornece a flexibilidade de configurar o bypass para as topologias mais comuns, porque permite um controle refinado de quando o bypass acontece, além de oferecer suporte às interações com o serviço de controle de admissão de chamadas (CAC). O sistema tentar facilitar sua tarefa, atribuindo automaticamente IDs de bypass conforme indicado a seguir.

- O sistema atribui automaticamente uma única ID de bypass exclusiva para cada região.

- Qualquer site conectado a uma região via link WAN, sem restrições de largura de banda, herda a mesma ID de bypass que a região.

- Um site associado à região via link WAN com largura de banda restrita é atribuído a uma ID de bypass diferente do da região.

- As sub-redes associadas a cada site herdam a ID de bypass do site.

## <a name="media-bypass-and-call-admission-control"></a>Bypass de mídia e controle de admissão de chamadas

O bypass de mídia e o CAC trabalham juntos para gerenciar o controle de largura de banda da mídia de chamadas. O bypass de mídia facilita o fluxo da mídia por links bem conectados, enquanto o bypass gerencia o tráfego nos links com limites de largura de banda. Como o Bypass de mídia e o CAC são mutuamente exclusivos, você deve estar atento a um quando estiver planejando o outro. Há suporte para as seguintes combinações:

- CAC e Bypass de mídia estão habilitados. O Bypass de mídia deve estar definido como **Use Site and Region Information** (Usar informações do site e da região). As informações do site e da região são as mesmas usadas no CAC.

    Se você habilitar o CAC, não poderá selecionar **ignorar sempre**e vice-versa, pois as duas configurações são mutuamente exclusivas. Ou seja, apenas um dos dois será aplicado a qualquer chamada PSTN. Primeiro, é feita uma verificação para determinar se a opção ignorar mídia se aplica à chamada. Em caso afirmativo, o CAC não é usado. Isso faz sentido, porque se uma chamada estiver qualificada para bypass, ela será por definição usando uma conexão em que o CAC não é necessário. Se bypass não puder ser aplicado à chamada (ou seja, se as IDs de bypass do cliente e do gateway não corresponderem), o CAC será aplicado à chamada.

- CAC não habilitado e Bypass de mídia definido como **Sempre ignorar**.

    Nesta configuração, as sub-redes do cliente e do tronco são mapeadas a uma única ID de bypass, que é computado pelo sistema.

- CAC não habilitado e Bypass de mídia definido é definido como **Use Site and Region Information** (Usar informações do site e da região).

    Onde **Use Site and Region Information** (Use Site and Region Information) estiver habilitado, a determinação do bypass funciona essencialmente da mesma maneira, independentemente de o CAC estar habilitado ou não. Ou seja, para qualquer chamada PSTN, a sub-rede do cliente é mapeada para um site específico, e a ID de bypass dessa sub-rede é extraída. Da mesma forma, a sub-rede do gateway é mapeada para um site específico, e a ID de bypass dessa sub-rede é extraída. O bypass só acontecerá para a chamada se as duas IDs de bypass forem idênticas. Caso não sejam idênticas, o bypass da chamada não acontecerá.

    Ainda que o CAC esteja desabilitado globalmente, a política de largura de banda precisa ser definida para cada site e link se você quiser usar a configuração site-e-região para controlar a decisão de bypass. O valor real da restrição de largura de banda ou sua modalidade não importa. O objetivo final é que o sistema calcule automaticamente as IDs diferentes de bypass para associar aos locais diferentes que não estão bem conectados. Definir a restrição da largura de banda por definição significa que um link não está bem conectado.

- O CAC está habilitado, mas o bypass de mídia não. Isso se aplica apenas onde todos os gateways e IP-PBXs não estão bem conectados ou não atendem outros requisitos para o bypass de mídia. Para obter detalhes sobre requisitos de bypass de mídia, consulte [Requirements for Media Bypass](https://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).

## <a name="technical-requirements"></a>Requisitos técnicos

Para cada chamada à PSTN, o servidor de mediação determina se a mídia do ponto de origem do Skype for Business pode ser enviada diretamente para um servidor de mediação de mesmo nível sem atravessar o servidor de mediação. O par pode ser um gateway PSTN, um IP-PBX ou um SBC (Controlador de Borda de Sessão) em um ITSP (provedor de serviços de telefonia da Internet) associado ao tronco entre o Servidor de Mediação para o qual a chamada é roteada.

O bypass de mídia pode ser empregado quando os seguintes requisitos são atendidos:

- Um peer do servidor de mediação deve dar suporte aos recursos necessários para o bypass de mídia, o mais importante é a capacidade de manipular várias respostas bifurcadas (conhecidas como "primeiras caixas de diálogo"). Contate o fabricante do seu gateway ou PBX ou seu ITSP para obter o valor do número máximo de caixas de diálogo iniciais que o gateway, o PBX ou o SBC pode aceitar.

- O par do servidor de mediação deve aceitar o tráfego de mídia diretamente dos pontos de extremidade do Skype for Business. Muitos ITSPs permitem que o SBC receba tráfego somente do servidor de mediação. Entre em contato com seu ITSP para determinar se o seu SBC aceita tráfego de mídia diretamente dos pontos de extremidade do Skype for Business.

- Os clientes do Skype for Business e um peer do servidor de mediação devem ser bem conectados, o que significa que estão localizados na mesma região de rede ou em sites de rede que se conectam à região em links de WAN que não têm restrições de largura de banda


