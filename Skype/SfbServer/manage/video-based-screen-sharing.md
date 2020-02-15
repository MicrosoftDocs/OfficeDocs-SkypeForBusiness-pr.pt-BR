---
title: Compartilhamento de tela baseado em vídeo para o Skype for Business Server
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
description: Informações de planejamento e configuração do Skype for Business Server para compartilhamento de tela baseado em vídeo (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009564"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Compartilhamento de tela baseado em vídeo para o Skype for Business Server 
 
O compartilhamento de tela baseado em vídeo (VbSS) no Skype for Business Server 2015 agora está disponível para download: [atualização cumulativa do Skype for Business server 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). O VbSS está incluído no Skype for Business Server 2019.
  
O compartilhamento de tela baseado em vídeo ou VbSS, aumentou o compartilhamento de tela do Lync. A diferença entre o VbSS e o compartilhamento de tela tradicional tem a ver com os protocolos subjacentes usados e o que eles acessam o Excel. O compartilhamento de tela usa o RDP (protocolo de área de trabalho remota), que é ótimo na criação de milhares de sessões de 1 a 1 entre os computadores de pessoas. A tecnologia mais nova, VbSS, utilizará o protocolo UDP (User Datagram Protocol).
  
O Skype for Business Server queria melhorar as conversas de um-para-1 e de suas reuniões de reunião e de terceiros. O VbSS usa a plataforma de mídia (que se baseia no UDP como o protocolo subjacente), com o objetivo de melhorar seus horários de início de vídeo, a qualidade de exibição do que você está assistindo (especialmente se o que você está assistindo estiver se movendo rapidamente) e a confiabilidade geral.
  
Parte da meta de melhorar o compartilhamento de tela é que a transição entre o VbSS e o RDP seja o mais uniforme possível quando eles ocorrem. Como o VbSS é uma atualização da tecnologia subjacente usada no compartilhamento de tela para o Skype for Business Server, pode ser difícil detectar a tecnologia que você está aproveitando, a menos que esteja examinando os detalhes SIP no tráfego de rede ou está compartilhando conteúdo que é movimentação rápida ou 3D. Se, por exemplo, seu local de trabalho tiver muitos clientes herdados, o RDP ainda estará disponível como uma FailSafe para suas reuniões e conversas. O Skype for Business Server usa a lógica interna para decidir quais dos dois métodos (VbSS ou o compartilhamento de tela tradicional) se aplicam quando os clientes se conectam. O RDP pode e será substituído por VbSS quando a situação solicitar, para que a experiência de visualização não seja interrompida.
  
## <a name="planning"></a>Planejamento

### <a name="vbss-pros-and-cons"></a>Prós e contras VbSS

Mudar para o VbSS destina-se a fazer três melhorias importantes:
  
1. Tornar o compartilhamento de tela (até 5%) mais confiável em comparação com o RDP sozinho.

2. Tornar a experiência de vídeo e a configuração da sessão mais rápida em comparação ao RDP sozinho (configuração na metade do tempo, com um aprimoramento de 6:1 em quadros por segundo).

3. Funciona muito melhor do que o RDP em condições de baixa largura de banda, mesmo ao compartilhar conteúdo de alta movimentação, como gráficos 3D.
    
Tenha em mente que esses números se baseiam no ajuste de desempenho adequado e de integridade da sua rede e podem envolver redes externas por conta própria, se seus clientes estiverem em dispositivos móveis.
  
Você também deve estar ciente de que alguma fidelidade/nitidez do seu conteúdo compartilhado foi negociada por confiabilidade, velocidade e eficiência. Na maioria dos casos, isso não será prontamente visível aos usuários.
  
### <a name="ports-and-protocols"></a>Portas e protocolos

**Portas de servidor necessárias**

|**Função de servidor**|**Nome do serviço**|**Porta ou intervalo de portas**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
   
**Portas de cliente necessárias**

|**Componente**|**Intervalo de portas**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Compartilhamento de aplicativos  <br/> |
   
Se a QoS estiver habilitada para as seguintes portas de mídia e o VbSS também estiver habilitado, durante uma conferência que inclui o compartilhamento de área de trabalho, o como MCU usará as configurações de porta de vídeo mostradas em negrito abaixo para o tráfego de compartilhamento de tela. 
  
> [!IMPORTANT]
> Essas configurações são um caso especial, e essas configurações exatas devem ser usadas ao implementar ambos os recursos. Isso substitui outras configurações recomendadas na [documentação de QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx). Para compartilhamento de aplicativos, você também precisará especificar o ASMCUSVC. exe no GPO de QoS, além de definir esses valores de porta. 
  
**Configurações obrigatórias de QoS/VbSS do servidor de aplicativos**

|**Propriedade**|**Valor da porta**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |VIA  <br/> |
|AudioPortCount  <br/> |8348  <br/> |VIA  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |VIA  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |VIA  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planejamento da capacidade

Cada servidor de front-end executando o Skype for Business Server 2015 atualização cumulativa 2 (CU2) ou posterior suporta até 375 participantes para compartilhamento de tela usando o RDP (embora apenas 250 por reunião). Essa capacidade não muda o CU3, quando o VbSS é introduzido e usado.
  
Dito isso, fizemos testes de desempenho e de estresse no nosso laboratório, e as medidas a seguir também devem ser consideradas em relação à sua própria implantação (dependendo do uso, naturalmente).
  
Pressupo
  
- Você está usando o Skype for Business Server 2015 CU2 ou posterior em sua implantação.
    
- Todos os usuários no ambiente do Skype for Business Server têm resoluções de tela mais altas do que 1920 x 1080.
    
Na capacidade total (que, conforme observado acima, é 375 compartilhamento de tela de participantes por servidor front-end no total, embora apenas 250 por reunião), o servidor front-end pode estar utilizando aproximadamente 89% do 1 Gigabit da placa de rede. Isso ocorre porque a tecnologia de compartilhamento de tela existente no Skype for Business Server CU2 (RDP) transmite o conteúdo na tela na resolução nativa do computador do apresentador. Assim, com as resoluções de tela mais altas, talvez você já esteja experimentando afunilamentos de rede para compartilhamento de tela com o Skype for Business Server 2015 CU2.
  
Para reduzir isso, uma ou mais das seguintes opções podem ser úteis:
  
- Atualize o servidor front-end de uma placa de rede de 1 Gigabit para uma placa Ethernet de 10 gigabits.

- Aumente o número de servidores front-end para o tráfego de balanceamento de carga.

- Limite a largura de banda (taxa de bits) usada para VbSS e RDP, colocando um limite na largura de banda máxima usada por ambos os canais.
    
Os números nesta tabela são influenciados por redes individuais e pelo conteúdo que está sendo compartilhado. Teste para estabelecer linhas de base para sua rede ou redes.
  
|**1080p de conteúdo**|**Média de RDP**|**Pico de RDP**|**Média de VbSS**|**Pico de VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|APRESENTAÇÃO  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|PROJETOS  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5mbps  <br/> |7mbps  <br/> |1,3 Mbps  <br/> |2,2 Mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia

A largura de banda do VbSS é:
  
|**Codec de vídeo**|**Resolução e taxa de proporção**|**Taxa máxima de bits de carga de vídeo (Kbps)**|**Taxa de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920 x 1080 (16:9)  <br/> (A taxa de proporção depende da resolução do monitor do participante do compartilhamento e nem sempre será 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Suporte a clientes e servidores

O compartilhamento de tela baseado em vídeo requer o Skype for Business Server 2015 CU3 ou posterior e uma versão atual dos clientes de suporte listados na [comparação de recursos do cliente móvel para o suporte do Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) e [reuniões](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Há situações em que o compartilhamento de tela passará para o RDP, da seguinte forma:
  
- Se sua conta estiver hospedada em um ambiente onde o ASMCU não atende à compilação mínima que dá suporte a VbSS.
- Se alguém que usa uma versão mais antiga do cliente Skype for Business ingressar em sua sessão, por exemplo, qualquer pessoa usando qualquer versão de cliente do Windows inferior a 16.0.6330.1000, dispositivos do sistema de sala do Skype for Business ou aplicativos móveis do Skype for Business. 
- Se um usuário estiver compartilhando do Skype for Business Web App.
- Se alguém está usando o Skype for Business no Mac e não está hospedado no Skype for Business online ou no Skype for Business Server 2015 com a atualização cumulativa de julho de 2018 (ou posterior).
- Se alguém iniciar qualquer compartilhamento de programa/Windows.
- Se alguém começar a gravar a sessão.
- Se alguém chamar o controle de tela remoto durante a sessão. 
- Reuniões com mais de 250 participantes (onde VbSS não tem suporte no momento).

Lembre-se de que, após a transição da sessão para o RDP, ela não fará a transição de volta para o VbSS. Novamente, a transição de VbSS é destinada a ser direta, e, com esperança, não será fácil de detectar na maioria das situações.
    
> [!NOTE]
> Não há suporte para bloquear, ou tentar bloquear, a transição do VbSS para o RDP no compartilhamento de tela do Skype for Business. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitar, desabilitar e configurar o VbSS

O grande aspecto é, depois de instalar a atualização cumulativa 3 (CU3) do Skype for Business Server 2015 ou posterior, todos os usuários serão habilitados para VbSS de 1 a 1 e de vários participantes por padrão. Isso pode ser problemático se você tiver um motivo para não ter essa funcionalidade habilitada para todos os seus usuários. Nesse caso, você poderá usar estas etapas para desabilitar os usuários (as etapas de habilitar usuários serão seguidas):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Como desabilitar os usuários de usar o VbSS

- Você pode atribuir uma política de usuário que não permite o VbSS a qualquer usuário que não esteja usando o VbSS executando esse cmdlet no console de gerenciamento do Skype for Business (substitua [PolicyName] pela política para a qual você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obter mais informações sobre este comando, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar desativar o VbSS completamente, poderá executar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obter mais informações sobre este comando, consulte [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião de vários participantes do Skype for Business, todos os pontos de extremidade do cliente respeitarão a configuração de política para o organizador da reunião. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Como permitir que os usuários usem o VbSS

- Você pode atribuir uma política de usuário específica que permite o VbSS a qualquer usuário que precise estar usando o VbSS executando esse cmdlet no console de gerenciamento do Skype for Business (substitua [PolicyName] pela política para a qual você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obter mais informações sobre este comando, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar ativar o VbSS novamente depois de desativá-lo (ele está ativado por padrão), você pode executar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obter mais informações sobre este comando, consulte [set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião de vários participantes do Skype for Business, todos os pontos de extremidade do cliente respeitarão a configuração de política para o organizador da reunião. 
  
## <a name="see-also"></a>Confira também

[Skype for Business Server 2015 atualização cumulativa KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[O compartilhamento de tela baseado em vídeo (VBSS) está disponível no Skype for Business Server 2015](https://support.microsoft.com/kb/3170163)
