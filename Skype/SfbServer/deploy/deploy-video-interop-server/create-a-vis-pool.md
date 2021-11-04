---
title: Criar um pool vis no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumo: Crie um pool de Servidores de Interop de Vídeo em Skype for Business Server usando o Construtor de Topologias.'
ms.openlocfilehash: e622c6510b23148617ad180ecc61480503a79a8a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748797"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Criar um pool vis no Skype for Business Server
 
**Resumo:** Crie um pool de Servidores de Interop de Vídeo em Skype for Business Server usando o Construtor de Topologias.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Criar um pool VIS ou VIS usando o Construtor de Topologias

1. Abra o Construtor de Topologias no servidor front-end. No painel esquerdo do Construtor de Topologias, clique com o botão direito do mouse em **Pools** de Servidores de Interop de Vídeo e escolha Novo Pool de Servidores **de Interop de Vídeo**. 
    
2. Isso abrirá um assistente Criar um novo Pool de Servidores **de Interop de** Vídeo. Forneça o FQDN do Pool para o novo Servidor de Interop de Vídeo e selecione Este **pool** tem um servidor ou Esse **pool** tem vários servidores com base em seu requisito e pressione **Next**.
    
    Se você quiser implantar um pool de Servidor de Interop de Vídeo para fornecer alta disponibilidade, selecione **Este pool tem vários servidores**. Tenha em mente esta opção que: 
    
    - Você deve implantar o balanceamento de carga DNS para dar suporte a pools de Servidor de Interop de Vídeo. 
    
   - Na próxima página, para Definir os computadores neste item do **pool,** insira o **FQDN** do computador de cada servidor no pool no campo de texto e clique em **Adicionar**. Repita esta etapa para adicionar outro Servidor de Interop de Vídeo ao pool. Quando você tiver definido todos os computadores no pool, pressione **Next**.
    
     Se você deseja implantar apenas um Servidor de Interop de Vídeo no pool porque não exige alta disponibilidade, selecione Este **pool** tem um servidor e pressione **Next**.
    
3. Selecione o pool/FE do próximo salto na listada e pressione **Next**.
    
4. Selecione um Pool de Borda para associar ao VIS e pressione **Concluir**.
    
5. Defina uma porta TCP ou TLS.
    
    Selecione o Servidor de Interop de Vídeo recém-adicionado no painel esquerdo do Construtor de Topologias, clique com o botão direito do mouse nele e escolha **Editar Propriedades**. Habilita ou atualize a porta TCP ou TLS de acordo com seu requisito e escolha **OK**. Embora por padrão o TLS seja adicionado, somente o TCP foi totalmente testado com o Gerenciador de Comunicações Unificadas da Cisco (CallManager ou CUCM).
    
6. Adicione um gateway de vídeo. Para fazer isso, expanda Componentes **Compartilhados,** clique com o botão direito do mouse em Gateways de Vídeo e selecione **Novo Gateway de Vídeo.**
    
7. Forneça o FQDN ou endereço IP do gateway de vídeo. O gateway de vídeo pode estar em um subdomínio ou em um domínio diferente. O CUCM usado pelos VTCs do sistema serve como um gateway de vídeo.
    
8. Selecione IPv4 ou IPv6 conforme apropriado. Você pode usar todos os endereços IP configurados ou limitar o uso do serviço a endereços IP selecionados.
    
9. Selecione a porta de escuta do gateway de vídeo. Selecione o protocolo de Transporte (TCP ou TLS) e associá-lo a um Servidor de Interop de Vídeo que está definido para um tronco SIP de vídeo. O Protocolo de Transporte para o gateway de vídeo deve corresponder ao Protocolo de Transporte configurado para o VIS.
    
10. Um tronco de vídeo SIP correspondente é adicionado após a conclusão da etapa acima. Clique com o botão direito do mouse no Tronco de Vídeo SIP e selecione o tronco que acabou de ser adicionado. O nome do tronco SIP de vídeo, o Servidor de Interop de Vídeo associado, o protocolo de Transporte SIP e a porta podem ser alterados. 
    
    > [!NOTE]
    >  Um Servidor de Interop de Vídeo dá suporte a troncos 1:N. Portanto, vários troncos podem ser adicionados, que são associados a um único Servidor de Interop de Vídeo, onde cada tronco termina em um Gateway de Vídeo diferente. A limitação é que um Gateway de Vídeo específico tem um único tronco que pode ser definido para a implantação Skype for Business Server.
  
11. Publique o Documento de Topologia conforme descrito em [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Para melhorar a resiliência, talvez você queira configurar um segundo Servidor de Interopção de Vídeo ou pool do VIS ou um pool de Front-End de backup. Consulte [Mecanismos de resiliência](../../plan-your-deployment/video-interop-server.md#resiliency) para obter mais informações.
  
Todas as tarefas executadas usando o Construtor de Topologias agora devem ser concluídas. Prossiga para instalar o software no novo servidor ou servidores VIS.
## <a name="see-also"></a>Confira também

[Implantar a função de servidor VIS Skype for Business Server](deploy-the-vis-server-role.md)

[Planejar o Servidor de Interop de Vídeo Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Criar e publicar nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
