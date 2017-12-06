---
title: "Como otimizar sua rede para o Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
description: "Os seguintes requisitos são realmente importantes para garantir a integridade de longo prazo e o sucesso para todos os Skype for Business Online recursos configura para sua organização. Sabemos que alguns de vocês são muito técnicos - este documento é para você, mas há algumas das que não estão. Se precisar de ajuda para configurar Skype for Business Online, você deve ler este documento para se familiarizar com as coisas que você precisa considerar. Também dará coisas para falar sobre quando você estiver trabalhando com o Centro de Fasttrackhttp Microsoft, o Microsoft Services e equipes de conta ou com parceiros Microsoft para descobrir como você pode atender a esses requisitos."
---

# Como otimizar sua rede para o Skype for Business Online

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](b363bdca-b00d-4150-96c3-ec7eab5a8a43.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43). 
  
Os seguintes requisitos são realmente importantes para garantir a integridade de longo prazo e o sucesso para todos os Skype for Business Online recursos configura para sua organização. Sabemos que alguns de vocês são muito técnicos - este documento é para você, mas há algumas das que não estão. Se precisar de ajuda para configurar Skype for Business Online, você deve ler este documento para se familiarizar com as coisas que você precisa considerar. Também dará coisas para falar sobre quando você estiver trabalhando com o [Centro de Fasttrackhttp Microsoft](https://fasttrack.microsoft.com/office), o Microsoft Services e equipes de conta ou com [parceiros Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search) para descobrir como você pode atender a esses requisitos.
  
## Uma rápida visão geral

O Skype for Business permite que você se conecte com colegas de trabalho ou parceiros de negócios na sua empresa ou em todo o mundo.
  
Com o Skype for Business, você pode:
  
- Iniciar conversas com mensagens instantâneas e chamadas de voz ou de vídeo.
    
- Veja quando seus contatos estão disponíveis online, em uma reunião ou fazendo uma apresentação.
    
- Defina segurança de nível industrial para reuniões.
    
- Faça transmissões online para um grande público.
    
-  Apresente sua tela durante reuniões ou dê o controle a outras pessoas.
    
- Usar o Skype for Business em outros programas do Office para conversar, fazer chamadas ou ingressar em uma reunião com um único clique.
    
## Por que tudo isso é tão importante?

A qualidade das mídias em tempo real (áudio, vídeo e compartilhamento de aplicativos) por meio de IP é bastante afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma excelente qualidade de mídia com o Skype for Business Online, é importante ter uma conexão de alta qualidade entre a rede da sua empresa e o Skype for Business Online. A melhor maneira de conseguir isso é configurar sua rede interna e a conectividade de nuvem com base na capacidade da sua rede para acomodar o volume de pico de tráfego do Skype for Business Online em todas as conexões.
  
Trabalhando com um [parceiros Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search), você pode conectar uma variedade de aplicativos do Office 365 incluem o Skype para Business Online na nuvem para sua rede e voz em tempo real e recursos de comunicações de vídeo para Skype para Business exigem serviços de rede devem ser configurados especificamente para oferecer suporte a essas cargas de trabalho em tempo real do Office 365. Isso inclui uma rede que tem largura de banda suficiente para executar o volume necessário de tráfego e ser capaz de oferecer suporte a qualidade do serviço (QoS) para proporcionar uma experiência de classe de negócios para seus usuários.
  
Juntamente com as informações aqui, há outros recursos que podem ajudar você a planejar e implantar os serviços e recursos do Skype for Business Online e garantir que seus serviços de rede cumpram esses requisitos:
  
- [Fluxo de chamadas usando Rota Expressa](call-flow-using-expressroute.md)
    
- [ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)
    
## Implementar a QoS (Qualidade de Serviço) para o Skype for Business

Antes de mover para o Skype for Business Online, você deve dar uma olhada capacidade da sua rede para lidar com áudio, vídeo e tráfego de sessão de compartilhamento. Como com outros serviços do Office 365, a Microsoft tem disponíveis para baixar o [Skype for Business Calculadora de largura de banda](https://www.microsoft.com/en-us/download/details.aspx?id=19011) que é usada para determinar o tráfego de rede necessários para cada um dos seus sites de empresa. Você deve executar modelagem de uso, incluindo modelagem fluxos de mídia de tráfego de comunicação em tempo real e a quantidade de Skype para o tráfego de negócios por localização de empresa, calcular o volume de tráfego e analisar como tráfego afeta sua rede geral. Depois que você terminar, a análise de dados deve fornecer recomendações de onde sua rede precisa ser melhorado e recomendar tamanhos de fila para fornecer uma experiência do usuário final excelente.
  
Skype para tráfego de negócios em tempo real é sensível à perda de pacotes, atraso e variação, que ocorrem com frequência nas redes congestionados. Qualidade do serviço (QoS) - às vezes chamado de serviço de classe - também deve ser implantada em WANs externos gerenciados, gerenciadas redes locais internos e redes de WiFi baseadas em enterprise. Isso ajudará a priorizar corretamente Skype para o tráfego de negócios em tempo real como áudio e vídeo sobre outro tráfego de tempo não real em redes locais e WAN, criando uma melhor experiência para os usuários finais.
  
Skype para áudio de negócios deve ser implantado no EF (acelerada encaminhamento - DSCP 46) fila e Skype para o vídeo de negócios devem ser implantado na AF41 (certeza encaminhamento - DSCP 34) fila. Isso é verdadeiro mesmo para tráfego de conferência e ponto-a-ponto, independentemente se o sistema telefônico no Office 365 ou outros recursos de telefonia estão sendo implantados.
  
Enquanto QoS existente políticas podem estar no lugar já na LAN e WAN para outros produtos de telefonia IP, Skype for Business permite aos usuários para ser móvel e para mover de local enquanto estiver usando o serviço. Por isso, as diretivas de QoS devem ser marcadas na LAN, WAN e redes sem fio para ter certeza de que todos os Skype para o tráfego de negócios está sendo priorizamos gerenciados em redes.
  
Para ajudar você a dimensionar sua rede, baixe a [Calculadora de Largura de Banda do Skype for Business](https://www.microsoft.com/en-us/download/details.aspx?id=19011).
  
Para saber mais sobre qualidade de mídia e QoS, veja [Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
Para obter mais informações sobre como configurar e gerenciar QoS, consulte [Gerenciamento de qualidade do serviço](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## Ignorar proxies e dispositivos de otimização de WAN

Todas as Office 365, incluindo o Skype for Business Online é criptografada e não é capaz de inspecionar por dispositivos de proxy normalmente. Por estes motivos recomendamos ignorando dispositivos de proxy para todo tráfego de rede do Office 365 conforme definido como seus usuários fazer [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)de conexões. Como os dispositivos de proxy provavelmente apresentará atraso em tempo real Skype for Business Online fluxos de mídia é altamente recomendável ignorando dispositivos de proxy no mínimo para que o tráfego.
  
A Microsoft recomenda a exclusão de URLs do Office 365 que usem arquivos PAC para enviar tráfego do Office 365 para um firewall. 
  
Aqui estão alguns recursos disponíveis que podem ajudar também:
  
- [Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Planejamento de rede e migração para o Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Gerador de PAC de proxy do Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Como usar o Controlador de Otimização de WAN ou dispositivos de tráfego/inspeção com o Office 365](https://aka.ms/kb2690045)
    
- [Roteamento com o ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## Ignorar a criptografia dupla

Para fornecer aos usuários a experiência de vídeo e áudio possível melhor, você deve implementar uma solução que impede que o Skype para mídia de negócios (áudio e vídeo) percorrer um túnel de rede Virtual privada (VPN). Todos os Skype para o tráfego de negócios é criptografados com segurança de camada de transporte (TLS) e as cargas de trabalho de mídia são criptografadas com o protocolo de Tempo Real seguro (SRTP). Sinalização é criptografada com TLS e as cargas de trabalho de mídia são criptografadas com SRTP. Enviando que esse tráfego através do túnel VPN adiciona uma camada extra de criptografia e saltos de rede adicional entre o cliente e o Office 365, que podem resultar em uma sessão degradada porque aumenta variação, perda de pacotes e latência.
  
Uma opção para evitar que o Skype para o tráfego de negócios percorrer túnel VPN é túnel em divisão. Para implementar a divisão de túnel, os clientes devem consultar com seus fornecedores de VPN nas especificações de como fazer isso no seu software.
  
> [!NOTE]
> Isso só é necessário para as cargas de trabalho de mídia do Skype for Business e não é aplicável a outros serviços do Office 365. 
  
Recursos adicionais:
  
- [Como permitir que a mídia do Lync ignore um túnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Mais sobre acesso direto, divisão de túnel e túnel forçado](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Habilitar acesso direto](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## Verifique se as portas e protocolos corretos estão abertos

Os clientes devem garantir a acessibilidade das URLs e endereços IP necessários para o serviço do O365. Para obter uma listagem completa de todos os endereços IP e URLs do Skype for Business Online, veja [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
  
Os clientes do Skype for Business usam uma variedade de portas e protocolos. A direção e o fluxo do tráfego de rede para uma sessão do Skype for Business variará dependendo do tipo das interações (ponto a ponto em comparação com multiparte) e dependendo do uso de compartilhamento de conteúdo e de voz/vídeo. Você deve examinar e abrir a lista de portas e protocolos, com especial atenção para as portas de origem e de destino. Por exemplo, o tráfego de áudio usa apenas 20 portas (50000-50019 TCP/UDP) no lado do cliente, mas a porta de destino pode estar em qualquer ponto de um intervalo de 10 mil portas (50000-59999 TCP/UDP) no lado do serviço. Isso também inclui a abertura de TCP 443 e UDP 3478 no firewall.
  
Uma configuração de rede adicional também pode ser necessária para suporte ao Skype for Business Online.
  
Você pode executar o teste FastTrack CloudApp de suas máquinas clientes para verificar se a configuração foi feita corretamente:
  
- **Para a América do Norte:**
    
  - [Análise Rápida de Rede do Office 365 (América do Norte)](http://na1-fasttrack.cloudapp.net/)
    
  - [https://137.117.72.96](https://137.117.72.96)
    
- **Para EMEA (Europa, Oriente Médio e África):**
    
  - [Análise Rápida de Rede do Office 365 (EMEA)](http://em1-fasttrack.cloudapp.net/)
    
  - [https://137.116.212.202](https://137.116.212.202)
    
- **Para APAC (Ásia-Pacífico):**
    
  - [Análise Rápida de Rede do Office 365 (Ásia-Pacífico)](http://ap1-fasttrack.cloudapp.net)
    
  - [https://168.63.169.67](https://168.63.169.67)
    
Você também pode ver, [Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## Usar telefones e dispositivos otimizados para o Skype for Business.

Em uma sessão de mídia em tempo real, dispositivos de mídia que são usados por todos os participantes, como headsets e webcams, têm grande impacto sobre a qualidade geral do áudio e do vídeo. Dispositivos de qualidade inferior ou com drivers incorretos produzirão uma qualidade geral inferior de som e imagem. Por outro lado, dispositivos certificados ou de boa qualidade ajudam a eliminar o eco, filtram ruídos, aumentam a resolução de vídeo e reduzem a latência.
  
Telefones e dispositivos fazem uma grande diferença na qualidade de áudio e vídeo para usuários finais. O Skype para o programa de certificação de negócios é uma evolução do programa "Lync compatível" e valida se o dispositivo atende aos padrões da Microsoft para áudio e vídeo. Há um número de telefones IP, USB dispositivos de áudio e vídeo, PCs e dispositivos de sala que tenham sido testados e qualificados pela Microsoft de reunião. Você deve examinar a lista de dispositivos que são otimizados para Skype for Business e o trabalho fornecer diferentes dispositivos para atender às necessidades de diversos e preferências pessoais dos usuários finais em sua organização.
  
Para obter mais informações sobre dispositivos aceitos e certificados, veja as seguintes referências:
  
- [Obter telefones para o Skype for Business Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Telefones e dispositivos para o Skype for Business](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Catálogo de soluções para periféricos pessoais](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Telefones e dispositivos qualificados para o Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
O ambiente e a área vizinha onde os usuários estão fazendo a reunião e usando dispositivos de áudio e vídeo são outro fator importante para a qualidade. Os usuários que fizerem chamadas em um ambiente barulhento terão áudio com eco, abafado e indistinto. Os usuários que estiverem em um ambiente escuro ou com pouca luz não obterão uma qualidade de imagem clara e viva. Em uma sala de conferência, o local do microfone e do dispositivo de vídeo afeta diretamente a qualidade do som e da imagem que os participantes receberão.
  
Para obter uma imagem mais clara de uso de experiência de áudio e vídeo de um usuário do Skype para o aplicativo de negócios **Ferramentas** > **Opções** > **Áudio** ou **Vídeo dispositivo** para fazer alterações no dispositivo em uso e personalizar configurações de TI. Você também pode verificar a qualidade de áudio de uma chamada clicando em **Verificar qualidade da chamada**. Se eles clicar em **Verificar qualidade da chamada**, em seguida, eles podem relatar a qualidade e problemas encontrados com a chamada de teste.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## Tópicos Relacionados

[ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

