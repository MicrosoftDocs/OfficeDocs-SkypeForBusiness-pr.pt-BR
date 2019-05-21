---
title: Criar um pool de VIS no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumo: criar um pool de servidores Interop de vídeo no Skype for Business Server usando o construtor de topologias.'
ms.openlocfilehash: 3e01659c4cef268a8748bd14c658eb5168b3ac97
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302725"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Criar um pool de VIS no Skype for Business Server
 
**Resumo:** Crie um pool de servidores de interoperabilidade de vídeo no Skype for Business Server usando o construtor de topologias.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Crie um pool VIS ou VIS usando o Construtor de Topologias

1. Abra o Construtor de Topologias no servidor de front-end. No painel esquerdo do construtor de topologias, clique com o botão direito do mouse em pools de **servidores Interop** e escolha **novo pool de servidores Interop de vídeo**. 
    
2. Isso abrirá um assistente **Criar um novo pool de servidor interop de vídeo**. Forneça o FQDN do pool para o novo servidor de interoperabilidade de vídeo e selecione **este pool tem um servidor** ou **esse pool tem vários servidores** com base em seu requisito e, em seguida, pressione **Avançar**.
    
    Se você quiser implantar um pool de servidores de interoperabilidade de vídeo para fornecer alta disponibilidade, selecione **este pool tem vários servidores**. Tenha em mente que com esta opção: 
    
    - Você deve implantar o balanceamento de carga de DNS para dar suporte a pools de servidores de interoperabilidade 
    
   - Na próxima página, no item **Definir os computadores neste pool**, insira o **FQDN do computador** de cada servidor no pool no campo de texto e clique em **Adicionar**. Repita esta etapa para adicionar outro servidor de interoperabilidade de vídeo ao pool. Quando você tiver definido todos os computadores no pool, aperte **Avançar**.
    
     Se você quiser implantar apenas um servidor de interoperabilidade de vídeo no pool porque não requer alta disponibilidade, selecione **este pool tem um servidor** e pressione **Avançar**.
    
3. Selecione o próximo pool/FE na lista suspensa e aperte **Avançar**.
    
4. Selecione um Pool de Borda para ser associado ao VIS e aperte **Concluir**.
    
5. Defina uma porta TCP ou TLS.
    
    Selecione o servidor de interoperabilidade de vídeo recém-adicionado no painel esquerdo do construtor de topologias, clique nele com o botão direito do mouse e escolha **Editar propriedades**. Habilite ou atualize a porta TCP ou TLS de acordo com o seu requisito e escolha **OK**. Embora o TLS padrão seja adicionado, somente o TCP foi totalmente testado com o Gerenciador de comunicações unificadas da Cisco (CallManager ou CUCM).
    
6. Adicione um gateway de vídeo. Para fazer isso, expanda os Componentes compartilhados, clique com o botão direito do mouse sobre **Gateways de vídeo** e selecione **Novo gateway de vídeo**.
    
7. Forneça o endereço IP ou FQDN do gateway de vídeo. O gateway de vídeo pode estar em um subdomínio ou em um domínio diferente. O CUCM usado pelos VTCs do seu sistema servem de gateway de vídeo.
    
8. Selecione IPv4 ou IPv6, conforme apropriado. Você pode usar todos os endereços IP configurados ou limitar o uso do serviço para endereços IP selecionados.
    
9. Selecione a porta de escuta do gateway de vídeo. Selecione o protocolo de transporte (TCP ou TLS) e associe-o a um servidor de interoperabilidade de vídeo que esteja configurado para um tronco de vídeo SIP. O Protocolo de Transporte para o gateway de vídeo deve ser correspondente ao Protocolo de Transporte configurado para o VIS.
    
10. Um tronco de vídeo SIP correspondente é adicionado após a conclusão da etapa acima. Clique com o botão direito do mouse sobre o tronco de vídeo SIP e selecione o tronco que acabou de ser adicionado. O nome do tronco SIP do vídeo, o servidor de interoperabilidade de vídeo associado, o protocolo de transporte SIP e a portabilidade podem ser alterados. 
    
    > [!NOTE]
    >  Um servidor de interoperabilidade de vídeo dá suporte A troncos 1: N. Portanto, vários troncos podem ser adicionados, que estão associados a um único servidor de interoperabilidade de vídeo, em que cada tronco termina em um gateway de vídeo diferente. A limitação é que um gateway de vídeo específico tem um e apenas um tronco que pode ser definido para a implantação do Skype for Business Server.
  
11. Publique o documento de topologia conforme descrito em [criar e publicar nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Para melhorar a resiliência, talvez você queira configurar um segundo servidor de interoperabilidade de vídeo ou um pool de VIS ou um pool de front-end de backup. Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para mais informações.
  
Todas as tarefas executadas usando o Construtor de Topologias devem estar concluídas. Prossiga com a instalação do software no novo servidor ou servidores VIS.
## <a name="see-also"></a>Confira também

[Implantar a função de servidor VIS no Skype for Business Server](deploy-the-vis-server-role.md)

[Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Criar e publicar uma nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
