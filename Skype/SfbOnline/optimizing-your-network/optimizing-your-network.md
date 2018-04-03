---
title: Otimizar sua rede
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Os seguintes requisitos são realmente importantes para garantir a integridade de longo prazo e o sucesso do Skype todos os recursos de Business Online você estiver configurando para sua organização. Nós sabemos que algumas das você são muito técnicas - este documento é para você, mas há algumas das que não são. Se você precisar de ajuda para configurar Skype para Business Online, você deve ler este documento para se familiarizar com as coisas que você precisa considerar. Ele também fornecerá a você as coisas para falar sobre quando você estiver trabalhando com Microsoft FastTrack Center, seu Microsoft Services e equipes de conta, ou com parceiros da Microsoft para descobrir como você pode atender a esses requisitos.
ms.openlocfilehash: 7817929f89731e13b09f5a6287493ea322b223d1
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Como otimizar sua rede para o Skype for Business Online

Os seguintes requisitos são realmente importantes para garantir a integridade de longo prazo e o sucesso do Skype todos os recursos de Business Online você estiver configurando para sua organização. Nós sabemos que algumas das você são muito técnicas - este documento é para você, mas há algumas das que não são. Se você precisar de ajuda para configurar Skype para Business Online, você deve ler este documento para se familiarizar com as coisas que você precisa considerar. Ele também fornecerá a você as coisas para falar sobre quando você estiver trabalhando com o [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), seu Microsoft Services e equipes de conta, ou com [parceiros da Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search) para descobrir como você pode atender a esses requisitos.
  
## <a name="a-quick-overview"></a>Uma rápida visão geral

O Skype for Business permite que você se conecte com colegas de trabalho ou parceiros de negócios na sua empresa ou em todo o mundo.
  
Com o Skype for Business, você pode:
  
- Iniciar conversas com mensagens instantâneas e chamadas de voz ou de vídeo.
    
- Ver quando seus contatos estão disponíveis online, em uma reunião ou fazendo uma apresentação.
    
- Definir segurança de nível industrial para reuniões.
    
- Fazer transmissões online para um grande público.
    
- Apresentar sua tela durante reuniões ou dar o controle a outras pessoas.
    
- Usar o Skype for Business em outros programas do Office para conversar, fazer chamadas ou ingressar em uma reunião com um único clique.
    
## <a name="why-is-this-all-so-important"></a>Por que tudo isso é tão importante?

A qualidade das mídias em tempo real (áudio, vídeo e compartilhamento de aplicativos) por meio de IP é bastante afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma excelente qualidade de mídia com o Skype for Business Online, é importante ter uma conexão de alta qualidade entre a rede da sua empresa e o Skype for Business Online. A melhor maneira de conseguir isso é configurar sua rede interna e a conectividade de nuvem com base na capacidade da sua rede para acomodar o volume de pico de tráfego do Skype for Business Online em todas as conexões.
  
Trabalhando com um [parceiro da Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search), você pode se conectar a uma variedade de aplicativos do Office 365 incluindo Skype para Business Online na nuvem para sua rede e voz em tempo real e recursos de comunicação de vídeo para Skype para negócios exigem rede serviços devem ser configurados especificamente para oferecer suporte a essas cargas de trabalho do Office 365 em tempo real. Isso inclui uma rede com largura de banda suficiente para transportar o volume de tráfego necessário e que pode dar suporte a Qualidade de Serviço (QoS) para oferecer uma experiência de classe empresarial aos usuários.
  
Juntamente com as informações aqui, há outros recursos que podem ajudar você a planejar e implantar os serviços e recursos do Skype for Business Online e garantir que seus serviços de rede cumpram esses requisitos:
  
- [Fluxo de chamadas usando Rota Expressa](call-flow-using-expressroute.md)
    
- [ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Implementar a QoS (Qualidade de Serviço) para o Skype for Business

Antes de migrar para o Skype for Business Online, você deve dar uma olhada na capacidade da sua rede para lidar com o tráfego de sessões de áudio, vídeo e compartilhamento. Tal como acontece com outros serviços do Office 365, a Microsoft tem disponível para download a [Calculadora de Largura de Banda do Skype for Business](https://www.microsoft.com/en-us/download/details.aspx?id=19011) que é usada para determinar o tráfego de rede necessário para cada um dos sites da empresa. Você deve realizar a modelagem de uso, incluindo a modelagem de fluxos de mídia de tráfego de comunicação em tempo real e a quantidade de tráfego do Skype for Business por local da empresa, o cálculo do volume de tráfego e a análise de como esse tráfego afeta sua rede de forma geral. Depois de ter feito isso, a análise desses dados deverá fornecer recomendações de onde sua rede precisa ser melhorada e recomendar tamanhos de fila para proporcionar uma excelente experiência do usuário final.
  
O tráfego em tempo real do Skype for Business é sensível à perda de pacotes, atraso e tremulação, que ocorrem frequentemente em redes congestionadas. A QoS (Qualidade de Serviço), às vezes chamada de Classe de Serviço, também deve ser implantada em WANs externas gerenciadas, LANs internas gerenciadas e redes Wi-Fi baseadas em empresas. Isso ajudará a priorizar adequadamente o tráfego em tempo real do Skype for Business, como áudio e vídeo, em vez de outro tráfego que não seja em tempo real nas redes locais e pela WAN, criando uma melhor experiência para os usuários finais.
  
O áudio do Skype for Business deve ser implantado na fila EF (Expedited Forwarding - DSCP 46), e o vídeo do Skype for Business deve ser implantado na fila AF41 (Assured Forwarding - DSCP 34). Isso é verdadeiro mesmo para tráfego de ponto a ponto e conferências, independentemente se o sistema telefônico no Office 365 ou outros recursos de telefonia estão sendo implantados.
  
Enquanto políticas de QoS existentes podem já estar em vigor na LAN e na WAN para outros produtos de telefonia IP, o Skype for Business proporciona mobilidade aos usuários, que podem se deslocar de um local para outro durante o uso do serviço. Por causa disso, as políticas de QoS devem ser marcadas na LAN, na WAN e em redes sem fio, a fim de ter certeza de que todo o tráfego do Skype for Business esteja sendo priorizado nas redes gerenciadas.
  
Para ajudar você a dimensionar sua rede, baixe a [Calculadora de Largura de Banda do Skype for Business](https://www.microsoft.com/en-us/download/details.aspx?id=19011).
  
Para saber mais sobre qualidade de mídia e QoS, veja [Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online](media-quality-and-network-connectivity-performance.md).
  
Para obter mais informações sobre como configurar e gerenciar o QoS, consulte [Gerenciando Quality of Service](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a>Ignorar proxies e dispositivos de otimização de WAN

Todo o Office 365, incluindo o Skype for Business Online, é criptografado e, normalmente, não pode ser inspecionado por dispositivos proxy. Por esses motivos, recomendamos que dispositivos proxy não sejam usados em todo o tráfego de rede do Office 365, como os definidos como conexões que os usuários fazem para [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Como há grande probabilidade de os dispositivos proxy ocasionarem atraso nos streams de mídia do Skype for Business Online em tempo real, recomendamos que eles sejam usados minimamente para esse tráfego.
  
A Microsoft recomenda a exclusão de URLs do Office 365 que usem arquivos PAC para enviar tráfego do Office 365 para um firewall.
  
Aqui estão alguns recursos disponíveis que podem ajudar também:
  
- [Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Planejamento de rede e migração para o Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Gerador de PAC de proxy do Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Como usar o Controlador de Otimização de WAN ou dispositivos de tráfego/inspeção com o Office 365](https://aka.ms/kb2690045)
    
- [Roteamento com o ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a>Ignorar a criptografia dupla

Para proporcionar aos usuários a melhor experiência possível de áudio e vídeo, você deve implementar uma solução que impeça a mídia (áudio e vídeo) do Skype for Business de atravessar um túnel de VPN (Rede Privada Virtual). Todo o tráfego do Skype for Business é criptografado com TLS (Segurança da Camada de Transporte), e as cargas de trabalho de mídia são criptografadas com SRTP (Protocolo em Tempo Real Seguro). A sinalização é criptografada com TLS, e as cargas de trabalho de mídia são criptografadas com SRTP. O envio desse tráfego pelo túnel VPN adiciona uma camada extra de criptografia e saltos adicionais da rede entre o cliente e o Office 365, ambos os quais podem resultar em uma sessão degradada, pois aumenta a tremulação, a perda de pacotes e a latência.
  
Uma opção para evitar que o tráfego do Skype for Business atravesse o túnel VPN é a divisão de túnel. Para implementar a divisão de túnel, os clientes devem consultar seu fornecedor de VPN sobre detalhes específicos de como fazer isso em seu software.
  
> [!NOTE]
> [!OBSERVAçãO] Isso só é necessário para as cargas de trabalho de mídia do Skype for Business e não é aplicável a outros serviços do Office 365. 
  
Recursos adicionais:
  
- [Como permitir que a mídia do Lync ignore um túnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Mais sobre acesso direto, divisão de túnel e túnel forçado](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Habilitar acesso direto](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a>Verifique se as portas e protocolos corretos estão abertos

Os clientes devem garantir a acessibilidade das URLs e endereços IP necessários para o serviço do O365. Para obter uma listagem completa de todos os endereços IP e URLs do Skype for Business Online, veja [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
  
Os clientes do Skype for Business usam uma variedade de portas e protocolos. A direção e o fluxo do tráfego de rede para uma sessão do Skype for Business variará dependendo do tipo das interações (ponto a ponto em comparação com multiparte) e dependendo do uso de compartilhamento de conteúdo e de voz/vídeo. Você deve examinar e abrir a lista de portas e protocolos, com especial atenção para as portas de origem e de destino. Por exemplo, o tráfego de áudio usa apenas 20 portas (50000-50019 TCP/UDP) no lado do cliente, mas a porta de destino pode estar em qualquer ponto de um intervalo de 10 mil portas (50000-59999 TCP/UDP) no lado do serviço. Isso também inclui a abertura de TCP 443 e UDP 3478 no firewall.
  
Uma configuração de rede adicional também pode ser necessária para suporte ao Skype for Business Online.
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Usar telefones e dispositivos otimizados para o Skype for Business.

Em uma sessão de mídia em tempo real, dispositivos de mídia que são usados por todos os participantes, como headsets e webcams, têm grande impacto sobre a qualidade geral do áudio e do vídeo. Dispositivos de qualidade inferior ou dispositivos com drivers de dispositivo incorreto causarão qualidade geral som inferior para qualidade de imagem de áudio e mais baixa para vídeo. Por outro lado, dispositivos certificados ou de boa qualidade ajudam a eliminar o eco, filtram ruídos, aumentam a resolução de vídeo e reduzem a latência.
  
Telefones e dispositivos fazem uma enorme diferença na qualidade do áudio e do vídeo para usuários finais. O programa de certificação do Skype for Business é uma evolução do programa "Compatível com Lync" e valida que o dispositivo atende aos padrões da Microsoft para áudio e vídeo. Há uma série de telefones IP, dispositivos de áudio e vídeo USB, computadores e dispositivos para salas de reuniões que foram testados e qualificados pela Microsoft. Você deve examinar a lista de dispositivos que são otimizados para o Skype for Business e trabalhar para fornecer diferentes dispositivos, a fim de atender às diferentes necessidades e preferências pessoais dos usuários finais na sua organização.
  
Para obter mais informações sobre dispositivos aceitos e certificados, veja as seguintes referências:  
  
- [Obter telefones para o Skype for Business Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Telefones e dispositivos para o Skype for Business](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Catálogo de soluções para periféricos pessoais](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Telefones e dispositivos qualificados para o Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
O ambiente e a área vizinha onde os usuários estão fazendo a reunião e usando dispositivos de áudio e vídeo são outro fator importante para a qualidade. Os usuários que fizerem chamadas em um ambiente barulhento terão áudio com eco, abafado e indistinto. Os usuários que estiverem em um ambiente escuro ou com pouca luz não obterão uma qualidade de imagem clara e viva. Em uma sala de conferência, o local do microfone e do dispositivo de vídeo afeta diretamente a qualidade do som e da imagem que os participantes receberão.
  
Para obter uma imagem mais nítida de uso de áudio e vídeo de experiência do usuário do Skype para o aplicativo de negócios **Ferramentas** > **Opções** > **Dispositivo de áudio** ou **Dispositivo de vídeo** para fazer alterações para o dispositivo em uso e personalizar as configurações de TI. Você também pode verificar a qualidade de áudio de uma chamada ao clicar em **Verificar qualidade da chamada**. Quando você clica em **Verificar Qualidade da Chamada**, é possível reportar a qualidade e os problemas encontrados na chamada de teste.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a>Tópicos relacionados 

[ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)
  
  
 
