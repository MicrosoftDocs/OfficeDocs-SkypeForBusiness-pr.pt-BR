---
title: Criar um pool VIS no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumo: Crie um pool de servidores de interoperabilidade de vídeo no Skype para Business Server usando o construtor de topologias.'
ms.openlocfilehash: f290da287dc4e45a35d5d088e331d2c2540585ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894709"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Criar um pool VIS no Skype para Business Server
 
**Resumo:** Crie um pool de servidores de interoperabilidade de vídeo no Skype para Business Server usando o construtor de topologias.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Crie um pool VIS ou VIS usando o Construtor de Topologias

1. Abra o Construtor de Topologias no servidor de front-end. No painel à esquerda do construtor de topologia, clique com o botão direito em **Pools de servidor de interoperabilidade de vídeo** e escolha **Novo Pool de servidor de interoperabilidade de vídeo**. 
    
2. Isso abrirá um assistente **Criar um novo pool de servidor interop de vídeo**. Fornecer o FQDN do Pool para o novo servidor de interoperabilidade de vídeo e selecione **pool com um servidor** ou **pool com vários servidores** com base em suas necessidades, em seguida, pressione **Avançar**.
    
    Se você deseja implantar um pool de servidores de interoperabilidade de vídeo para fornecer alta disponibilidade, selecione o **pool com vários servidores**. Tenha em mente que com esta opção: 
    
    - Você deve implantar o balanceamento de carga DNS para dar suporte a pools de servidor de interoperabilidade de vídeo. 
    
   - Na próxima página, no item **Definir os computadores neste pool**, insira o **FQDN do computador** de cada servidor no pool no campo de texto e clique em **Adicionar**. Repita essa etapa para adicionar outro servidor de interoperabilidade de vídeo para o pool. Quando você tiver definido todos os computadores no pool, aperte **Avançar**.
    
     Se desejar implantar apenas um servidor de interoperabilidade de vídeo no pool, pois você não requerem alta disponibilidade, em seguida, selecione o **pool com um servidor** e pressione **Avançar**.
    
3. Selecione o próximo pool/FE na lista suspensa e aperte **Avançar**.
    
4. Selecione um Pool de Borda para ser associado ao VIS e aperte **Concluir**.
    
5. Defina uma porta TCP ou TLS.
    
    Selecione o servidor recém-adicionado de interoperabilidade de vídeo do painel esquerdo do construtor de topologia, clique com botão direito-lo e escolha **Editar propriedades**. Habilite ou atualize a porta TCP ou TLS de acordo com o seu requisito e escolha **OK**. Embora por padrão o TLS é adicionado, apenas TCP foi totalmente testado com Cisco Unified Communications Manager (CallManager ou CUCM).
    
6. Adicione um gateway de vídeo. Para fazer isso, expanda os Componentes compartilhados, clique com o botão direito do mouse sobre **Gateways de vídeo** e selecione **Novo gateway de vídeo**.
    
7. Forneça o endereço IP ou FQDN do gateway de vídeo. O gateway de vídeo pode estar em um subdomínio ou em um domínio diferente. O CUCM usado pelos VTCs do seu sistema servem de gateway de vídeo.
    
8. Selecione IPv4 ou IPv6, conforme apropriado. Você pode usar todos os endereços IP configurados ou limitar o uso do serviço para endereços IP selecionados.
    
9. Selecione a porta de escuta do gateway de vídeo. Selecione o protocolo de transporte (TCP ou TLS) e associá-lo a um servidor de interoperabilidade de vídeo, que é configurada para um tronco SIP de vídeo. O Protocolo de Transporte para o gateway de vídeo deve ser correspondente ao Protocolo de Transporte configurado para o VIS.
    
10. Um tronco de vídeo SIP correspondente é adicionado após a conclusão da etapa acima. Clique com o botão direito do mouse sobre o tronco de vídeo SIP e selecione o tronco que acabou de ser adicionado. O nome do tronco SIP vídeo, associados servidor interoperabilidade de vídeo, o protocolo de transporte SIP e porta pode todos ser alterada. 
    
    > [!NOTE]
    >  Um servidor de interoperabilidade de vídeo oferece suporte a troncos 1: n. Daí troncos múltiplos podem ser adicionados, que estão associados um único servidor de interoperabilidade de vídeo, onde cada tronco finaliza em um Gateway de vídeo diferentes. A limitação é que um Gateway de vídeo específico tem somente um tronco que pode ser definidas para o Skype para implantação de servidor de negócios.
  
11. Publicar o documento de topologia, conforme descrito em [criar e publicar a nova topologia no Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Para melhorar a resiliência, convém configurar um pool de servidor de interoperabilidade de vídeo ou VIS segundo ou um pool de Front-End de backup. Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para mais informações.
  
Todas as tarefas executadas usando o Construtor de Topologias devem estar concluídas. Prossiga com a instalação do software no novo servidor ou servidores VIS.
## <a name="see-also"></a>Confira também

[Implantar a função de servidor VIS no Skype para Business Server](deploy-the-vis-server-role.md)

[Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Criar e publicar uma nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
