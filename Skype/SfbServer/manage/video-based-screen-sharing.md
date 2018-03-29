---
title: Compartilhamento de tela baseado em vídeo do Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 'Skype para obter informações de planejamento e configuração de Business Server 2015 para vídeo com base no compartilhamento de tela (VbSS), que agora está disponível para download: Skype para KB3061064 de atualização cumulativa do Business Server 2015.'
ms.openlocfilehash: 21b7868efb9b1a6621aa85cae277114629d67551
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="video-based-screen-sharing-for-skype-for-business-server-2015"></a>Compartilhamento de tela baseado em vídeo do Skype for Business Server 2015
 
Skype para obter informações de planejamento e configuração de Business Server 2015 para vídeo com base no compartilhamento de tela (VbSS), que agora está disponível para download: [Skype para KB3061064 de atualização cumulativa do Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=47690).
  
Vídeo com base no compartilhamento de tela ou VbSS, cresceram sair do Lync o compartilhamento de tela. A diferença entre o VbSS e o compartilhamento de tela tradicional reside nos protocolos subjacentes usados e nas melhorias apresentadas. O compartilhamento de tela usa o protocolo RDP, que é ótimo para criar múltiplas sessões privadas (entre dois participantes) entre os computadores dos usuários. Tecnologia mais recente, o VbSS usará o protocolo UDP.
  
Skype para Business Server queria melhorar 1-para-1 pessoas e suas conversas de 1-para-muitos (com vários participantes) e experiências de reunião. O VbSS utiliza a plataforma de mídia (que tem UDP como o protocolo subjacente), com o objetivo de aprimorar os tempos de inicialização de vídeo, a qualidade de exibição do que se está assistindo (especialmente se o objeto estiver se movendo rapidamente) e a confiabilidade em geral.
  
Parte o objetivo de melhorar o compartilhamento de tela é que transições entre VbSS e RDP ser tão uniforme possível quando ocorrem. Como VbSS é uma atualização para tecnologia subjacente que é usada na tela de compartilhamento do Skype para Business Server, pode ser difícil detectar qual tecnologia que você esteja aproveitando a menos que você estiver examinando detalhes do SIP o tráfego de rede ou que esteja compartilhando conteúdo está movendo fast ou 3D. Se, por exemplo, seu local de trabalho tiver muitos clientes herdados, RDP ainda estará disponível como à prova de falha para as reuniões e conversas. Skype para Business Server usa lógica interna para decidir qual dos dois métodos (VbSS ou compartilhamento de tela tradicional) a ser aplicada quando os clientes se conectam. RDP pode e, substituirá VbSS quando a situação ligar para ele, para que a sua experiência de exibição não será interrompida.
  
## <a name="planning"></a>Planejamento

### <a name="vbss-pros-and-cons"></a>Prós e contras do VbSS

A mudança para o VbSS tem como objetivo três melhorias principais:
  
1. Tornar o compartilhamento de tela (até 5%) mais confiável em comparação com o RDP sozinho.

2. Tornar a configuração da sessão e a experiência de vídeo mais rápida em comparação com o RDP sozinho (configuração na metade do tempo, com um aprimoramento de 6:1 nos quadros por segundo).

3. Funciona muito melhor que o RDP em condições de baixa largura de banda, mesmo quando o conteúdo de compartilhamento apresenta alta movimentação, como gráficos 3D.
    
Lembre-se que esses números dependem da integridade e do ajuste de desempenho apropriado de sua rede e podem envolver redes externas à sua, se os clientes estiverem em dispositivos móveis.
  
Esteja também ciente de que certo nível de fidelidade/definição de seu conteúdo compartilhado foi trocado por confiabilidade, velocidade e eficiência. Na maioria dos casos, isso não estará prontamente visível aos usuários.
  
### <a name="ports-and-protocols"></a>Portas e protocolos

**Portas do servidor necessárias**

|**Função de servidor**|**Nome do serviço**|**Porta ou intervalo**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
   
**Portas necessárias do cliente**

|**Componente**|**Intervalo de portas**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Compartilhamento de aplicativos.  <br/> |
   
Se o QoS estiver habilitado para as seguintes portas de mídia e VbSS também está habilitado, durante uma conferência que inclui o compartilhamento da área de trabalho que como MCU usará as configurações de porta de vídeo mostradas na negrito abaixo para o tráfego de compartilhamento de tela. 
  
> [!IMPORTANT]
> Essas configurações são um caso especial, e essas configurações exatas devem ser usadas ao implementar esses recursos. Isso substitui outras configurações recomendadas na [documentação de QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). Aplicativo FO compartilhamento que você também precisará especificar ASMCUSVC.exe do GPO QoS, além de definir esses valores de porta. 
  
**Configurações do servidor de aplicativo QoS/VbSS necessárias**

|**Propriedade**|**Valor da porta**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>Planejamento de capacidade

Cada servidor Front-End executando o Skype para Business Server 2015 atualização cumulativa 2 (CU2) suporta até 375 participantes para a tela de compartilhamento usando RDP (embora apenas 250 por reunião). Essa capacidade não muda após a CU3, quando o VbSS é introduzido e usado.
  
Dito isso, realizamos testes de desempenho e de estresse em nosso laboratório, e as seguintes avaliações também devem ser consideradas em relação à sua própria implantação (dependendo do uso).
  
Supondo que:
  
- Você está usando Skype para Business Server 2015 CU2 em sua implantação.
    
- Todos os usuários em sua Skype para ambiente de servidor de negócios tem resoluções de tela mais que 1920 x 1080.
    
Em plena capacidade (que conforme descrito acima, é 375 participantes de compartilhamento de tela por servidor Front-End no total, embora somente 250 por reunião), o servidor Front-End utilizando a ~ 89% de 1 Gigabit da placa de rede. Isso ocorre porque a tela existente tecnologia Skype de compartilhamento para o Business Server CU2 (RDP) transmite o conteúdo na tela com a resolução nativa do PC do apresentador. Isso com resoluções de tela superior acrescentadas, você pode já estar enfrentando afunilamentos de rede para a tela compartilhando com Skype para Business Server 2015 CU2.
  
Para minimizar isso, uma ou mais das seguintes opções podem ser úteis:
  
- Atualize seu servidor Front-End de uma placa de rede de Gigabit 1 em um cartão de Gigabit Ethernet 10.

- Aumente o número de servidores Front-End para o tráfego de balanceamento de carga.

- Limite a largura de banda (taxa de bits) usada para VbSS e RDP definindo um limite máximo para a largura de banda usada por ambos os canais.
    
Os números nesta tabela são afetados por redes individuais e pelo conteúdo compartilhado. Faça testes para estabelecer as linhas de base para suas redes.
  
|**Conteúdo 1080p**|**Média RPD**|**Pico de RDP**|**Média de VbSS**|**Pico VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12Mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5Mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2Mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia

A largura de banda do VbSS é:
  
|**Codec de vídeo**|**Resolução e taxa de proporção**|**Taxa de bits de carga de vídeo máxima (Kbps)**|**Taxa de bits de vídeo de carga mínima (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920 x1080 (16:9)  <br/> (A taxa de proporção depende da resolução do monitor do usuário participante do compartilhamento e nem sempre será de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Suporte a clientes e servidores

Compartilhamento de tela com base em vídeo requer Skype para Business Server 2015 CU3 ou posterior e uma versão atual dos clientes suportados listados na [comparação de recursos do cliente móvel para Skype para os negócios](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) e [suportam de reuniões](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Existem situações em que o compartilhamento de tela farão a transição para RDP, como estes:
  
- Se sua conta estiver hospedada em um ambiente em que o ASMCU não atende ao build mínimo compatível com VbSS.
- Se alguém que usa uma versão mais antiga do Skype para o cliente de negócios ingressa em uma sessão, por exemplo qualquer pessoa usando qualquer versão de cliente do Windows que é menor que 16.0.6330.1000, Skype para dispositivos de sistema de sala de negócios ou Skype Mobile nos aplicativos de negócios. 
- Se um usuário está compartilhando a partir do Skype para negócios Web App.
- Se uma pessoa está usando o Skype para Businesson Mac e não estiver hospedada no Skype para negócios Online.
- Se alguém inicia o Compartilhamento de Programa/Windows, e/ou gravação durante a sessão.
- Se alguém solicita Controle de Tela Remoto durante a sessão.

    Esteja ciente de que, após a transição da sessão para RDP, ela não transitará de volta para VbSS. Reforçando, a transição do VbSS deverá ocorrer sem problemas e, provavelmente, será imperceptível na maioria das situações.
  
- Reuniões com mais de 250 participantes (às quais o VbSS não dá suporte no momento).
    
> [!NOTE]
> Ele não tem suporte para bloquear ou tentar bloquear, a transição do VbSS para RDP no Skype para compartilhamento de tela de negócios. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitando, desabilitando e configurando o VbSS

A grande vantagem é, depois que você instalou o Skype para Business Server 2015 atualização cumulativa 3 (CU3), todos os usuários serão habilitados para VbSS 1-para-1 e com vários participantes por padrão. Isso pode ser um problema para você, caso não deseje habilitar essa funcionalidade para todos os usuários. Nesse caso, siga as etapas abaixo para desabilitar usuários (as etapas para habilitar usuários serão apresentadas posteriormente):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Como desabilitar usuários para uso do VbSS

- Você pode atribuir uma política de usuário que não permitem que VbSS todos os usuários que não deveriam estar usando VbSS executando este cmdlet no Skype para o Console de gerenciamento de negócios (replace [PolicyName] com a política para que estiver fazendo isso):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obter mais informações sobre esse comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar desativar o VbSS completamente, poderá executar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obter mais informações sobre esse comando, consulte [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em um Skype com vários participantes para a reunião de negócios, todos os pontos de extremidade do cliente respeitam a configuração de diretiva para o organizador da reunião. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Como habilitar usuários para o uso do VbSS

- Você pode atribuir uma política de usuário específico que permite VbSS para todos os usuários que precisam estar usando VbSS executando este cmdlet no Skype para o Console de gerenciamento de negócios (replace [PolicyName] com a política para que estiver fazendo isso):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obter mais informações sobre esse comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar ativar novamente o VbSS depois de desativá-lo (ele é ativado por padrão), poderá executar este comando:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obter mais informações sobre esse comando, consulte [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em um Skype com vários participante para a reunião de negócios, todos os pontos de extremidade do cliente respeitam a configuração de diretiva para o organizador da reunião. 
  
## <a name="see-also"></a>Consulte também

#### 

[Skype para Business Server 2015 atualização cumulativa KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[Vídeo com base no compartilhamento de tela (VBSS) está disponível no Skype para Business Server 2015](https://support.microsoft.com/en-us/kb/3170163)

