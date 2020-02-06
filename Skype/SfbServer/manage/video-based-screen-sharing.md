---
title: Compartilhamento de tela baseado em vídeo do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informações de planejamento e configuração do Skype for Business Server para compartilhamento de tela com base em vídeo (VbSS)
ms.openlocfilehash: f0d474772b94389c1d69264be61b3bee2b46a385
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817041"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Compartilhamento de tela baseado em vídeo do Skype for Business Server 
 
O compartilhamento de tela baseado em vídeo (VbSS) no Skype for Business Server 2015 agora está disponível para download: o [Skype for Business server 2015 atualização cumulativa KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690). O VbSS está incluído no Skype for Business Server 2019.
  
O compartilhamento de tela com base em vídeo, ou VbSS, aumentou o compartilhamento de tela do Lync. A diferença entre o VbSS e o compartilhamento de tela tradicional reside nos protocolos subjacentes usados e nas melhorias apresentadas. O compartilhamento de tela usa o protocolo RDP, que é ótimo para criar múltiplas sessões privadas (entre dois participantes) entre os computadores dos usuários. Tecnologia mais recente, o VbSS usará o protocolo UDP.
  
O Skype for Business Server queria melhorar as conversas de uma pessoa para a outra e as experiências de reunião e de um para muitos (vários participantes). O VbSS utiliza a plataforma de mídia (que tem UDP como o protocolo subjacente), com o objetivo de aprimorar os tempos de inicialização de vídeo, a qualidade de exibição do que se está assistindo (especialmente se o objeto estiver se movendo rapidamente) e a confiabilidade em geral.
  
Parte da meta de melhorar o compartilhamento de tela é que as transições entre o VbSS e o RDP sejam tão simples quanto possível quando ocorrem. Como o VbSS é uma atualização da tecnologia subjacente usada no compartilhamento de tela do Skype for Business Server, pode ser difícil detectar a tecnologia que você está aproveitando, a menos que você esteja vendo os detalhes do SIP no tráfego de rede ou esteja compartilhando conteúdo que é movimentação rápida ou 3D. Se, por exemplo, seu local de trabalho tiver muitos clientes herdados, o RDP ainda estará disponível como uma falha de failsafe nas reuniões e conversas. O Skype for Business Server usa a lógica interna para decidir qual dos dois métodos (VbSS ou compartilhamento de tela tradicional) deve ser aplicado quando os clientes se conectam. O RDP pode e será substituído por VbSS quando a situação exigir, para que a experiência de visualização não seja interrompida.
  
## <a name="planning"></a>Planejamento

### <a name="vbss-pros-and-cons"></a>Prós e contras do VbSS

A mudança para o VbSS tem como objetivo três melhorias principais:
  
1. Tornar o compartilhamento de tela (até 5%) mais confiável em comparação com o RDP sozinho.

2. Tornar a configuração da sessão e a experiência de vídeo mais rápida em comparação com o RDP sozinho (configuração na metade do tempo, com um aprimoramento de 6:1 nos quadros por segundo).

3. Funciona muito melhor que o RDP em condições de baixa largura de banda, mesmo quando o conteúdo de compartilhamento apresenta alta movimentação, como gráficos 3D.
    
Lembre-se que esses números dependem da integridade e do ajuste de desempenho apropriado de sua rede e podem envolver redes externas à sua, se os clientes estiverem em dispositivos móveis.
  
Esteja também ciente de que certo nível de fidelidade/definição de seu conteúdo compartilhado foi trocado por confiabilidade, velocidade e eficiência. Na maioria dos casos, isso não estará prontamente visível aos usuários.
  
### <a name="ports-and-protocols"></a>Portas e protocolos

**Portas de servidor necessárias**

|**Função de servidor**|**Nome do serviço**|**Porta ou intervalo de portas**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
   
**Portas de cliente necessárias**

|**Componente**|**Intervalo de portas**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Compartilhamento de aplicativos.  <br/> |
   
Se a QoS estiver habilitada para as seguintes portas de mídia e VbSS também estiver habilitada, durante uma conferência que inclua o compartilhamento de área de trabalho, a a MCU usará as configurações de porta de vídeo mostradas em negrito abaixo para o tráfego de compartilhamento de tela. 
  
> [!IMPORTANT]
> Essas configurações são um caso especial, e essas configurações exatas devem ser usadas ao implementar esses dois recursos. Isso substitui outras configurações recomendadas na [documentação de QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). Para compartilhamento de aplicativos, você também precisará especificar o ASMCUSVC. exe no GPO de QoS, além de definir esses valores de portabilidade. 
  
**Configurações obrigatórias de QoS/VbSS do servidor de aplicativos**

|**Propriedade**|**Valor da porta**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planejamento de capacidade

Cada servidor front-end que executa o Skype for Business Server 2015 atualização cumulativa 2 (CU2) ou posterior oferece suporte a até 375 participantes para compartilhamento de tela usando RDP (mas somente 250 por reunião). Essa capacidade não muda após a CU3, quando o VbSS é introduzido e usado.
  
Dito isso, realizamos testes de desempenho e de estresse em nosso laboratório, e as seguintes avaliações também devem ser consideradas em relação à sua própria implantação (dependendo do uso).
  
Supondo que:
  
- Você está usando o Skype for Business Server 2015 CU2 ou posterior na sua implantação.
    
- Todos os usuários no ambiente do Skype for Business têm resoluções de tela superiores à 1920x1080.
    
Com a capacidade total (que, conforme observado acima, é o 375 compartilhamento de tela dos participantes por servidor front-end, mas somente 250 por reunião), seu servidor front-end pode estar utilizando aproximadamente 89% do 1 Gigabit da placa de rede. Isso ocorre porque a tecnologia de compartilhamento de tela existente no Skype for Business Server CU2 (RDP) transmite o conteúdo na tela na resolução nativa do PC do apresentador. Portanto, com as resoluções de tela mais altas, você pode já estar experimentando afunilamentos de rede para compartilhamento de tela com o Skype for Business Server 2015 CU2.
  
Para minimizar isso, uma ou mais das seguintes opções podem ser úteis:
  
- Atualize o servidor front-end de uma placa de rede de 1 Gigabit para um cartão Ethernet de 10 gigabits.

- Aumente o número de servidores front-end para tráfego de balanceamento de carga.

- Limite a largura de banda (taxa de bits) usada para VbSS e RDP definindo um limite máximo para a largura de banda usada por ambos os canais.
    
Os números nesta tabela são afetados por redes individuais e pelo conteúdo compartilhado. Faça testes para estabelecer as linhas de base para suas redes.
  
|**Conteúdo de 1080p **|**Média de RDP**|**RDP de pico**|**VbSS médio**|**VbSS de pico**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia

A largura de banda do VbSS é:
  
|**Codec de vídeo**|**Resolução e taxa de proporção**|**Taxa de bits máxima de carga de vídeo (Kbps)**|**Taxa de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920 x1080 (16:9)  <br/> (A taxa de proporção depende da resolução do monitor do usuário participante do compartilhamento e nem sempre será de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Suporte a clientes e servidores

O compartilhamento de tela baseado em vídeo requer o Skype for Business Server 2015 CU3 ou posterior, e uma versão atual dos clientes de suporte listados na [comparação de recursos do cliente móvel para suporte ao Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) e [reuniões](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Há situações em que o compartilhamento de tela fará a transição para o RDP, assim:
  
- Se sua conta estiver hospedada em um ambiente em que o ASMCU não atende ao build mínimo compatível com VbSS.
- Se alguém que usa uma versão mais antiga do cliente Skype for Business ingressar em sua sessão, por exemplo, qualquer pessoa que estiver usando qualquer versão de cliente do Windows inferior a 16.0.6330.1000, dispositivos do sistema de sala do Skype for Business ou aplicativos móveis do Skype for Business. 
- Se um usuário estiver compartilhando a partir do Skype for Business Web App.
- Se alguém estiver usando o Skype for Business no Mac e não estiver hospedado no Skype for Business online ou no Skype for Business Server 2015, com a atualização cumulativa de julho de 2018 (ou posterior).
- Se alguém iniciar qualquer programa/compartilhamento do Windows.
- Se alguém começar a gravar a sessão.
- Se alguém solicita Controle de Tela Remoto durante a sessão. 
- Reuniões com mais de 250 participantes (às quais o VbSS não dá suporte no momento).

Esteja ciente de que, após a transição da sessão para RDP, ela não transitará de volta para VbSS. Reforçando, a transição do VbSS deverá ocorrer sem problemas e, provavelmente, será imperceptível na maioria das situações.
    
> [!NOTE]
> Não há suporte para bloquear ou tentar bloquear, fazer a transição do VbSS para o RDP no compartilhamento de tela do Skype for Business. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitando, desabilitando e configurando o VbSS

A grande vantagem é que, depois de instalar a atualização cumulativa 3 (CU3) do Skype for Business Server 2015 ou posterior, todos os usuários serão habilitados para VbSS entre 1 e entre outros, por padrão. Isso pode ser um problema para você, caso não deseje habilitar essa funcionalidade para todos os usuários. Nesse caso, siga as etapas abaixo para desabilitar usuários (as etapas para habilitar usuários serão apresentadas posteriormente):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Como desabilitar usuários para uso do VbSS

- Você pode atribuir uma política de usuário que não permita o VbSS a nenhum usuário que não esteja usando o VbSS executando esse cmdlet no console de gerenciamento do Skype for Business (substitua [PolicyName] pela política para a qual você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obter mais informações sobre esse comando, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar desativar o VbSS completamente, poderá executar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obter mais informações sobre esse comando, consulte [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião de vários participantes do Skype for Business, todos os pontos de extremidade do cliente respeitarão a configuração de política para o organizador da reunião. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Como habilitar usuários para o uso do VbSS

- Você pode atribuir uma política de usuário específica que permita ao VbSS qualquer usuário que precise estar usando o VbSS executando esse cmdlet no console de gerenciamento do Skype for Business (substitua [PolicyName] pela política para a qual você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obter mais informações sobre esse comando, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar ativar novamente o VbSS depois de desativá-lo (ele é ativado por padrão), poderá executar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obter mais informações sobre esse comando, consulte [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião de vários participantes do Skype for Business, todos os pontos de extremidade do cliente respeitarão a configuração de política para o organizador da reunião. 
  
## <a name="see-also"></a>Confira também

[Skype for Business Server 2015 atualização cumulativa KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[O compartilhamento de tela baseado em vídeo (VBSS) está disponível no Skype for Business Server 2015](https://support.microsoft.com/en-us/kb/3170163)
