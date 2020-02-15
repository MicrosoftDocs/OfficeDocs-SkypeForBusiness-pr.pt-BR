---
title: Instalar ferramentas administrativas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumo: saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018262"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalar ferramentas administrativas no Skype for Business Server
 
**Resumo:** Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no centro de avaliação da Microsoft em [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
As ferramentas administrativas incluem o construtor de topologias e o painel de controle. As ferramentas administrativas devem ser instaladas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional do Windows que seja compatível com o Skype for Business Server. Você pode executar as etapas 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 em ordem e depois das etapas de 1 a 5, conforme descrito no diagrama. A instalação das ferramentas administrativas é a etapa 3 de 8.
  
![Diagrama de visão geral](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instalar ferramentas administrativas do Skype for Business Server

A mídia de instalação do Skype for Business Server oferece uma experiência flexível. Quando você executa o setup. exe pela primeira vez, as únicas ferramentas instaladas são o assistente de implantação do Skype for Business Server e o Shell de gerenciamento do Skype for Business Server. Usando essas duas ferramentas, conhecidas como componentes principais, você pode continuar com o processo de instalação, mas eles não oferecem a funcionalidade principal para o ambiente do Skype for Business Server geral. O assistente de implantação é iniciado automaticamente após a instalação dos componentes principais. A seção do assistente de implantação intitulado **instalar ferramentas administrativas** instala o construtor de topologias do Skype for Business Server e o painel de controle do Skype for Business Server.
  
> [!IMPORTANT]
> Todo ambiente do Skype for Business Server deve ter pelo menos um servidor com as ferramentas administrativas instaladas. 
  
Assista as etapas de vídeo para **instalar as ferramentas administrativas**:
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instalar as ferramentas administrativas do Skype for Business Server a partir do assistente de implantação

1. Insira a mídia de instalação do Skype for Business Server. Se a instalação não começar automaticamente, clique duas vezes em **configuração**.
    
2. A mídia de instalação requer que o Microsoft Visual C++ seja executado. Uma caixa de diálogo será exibida perguntando se você deseja instalá-la. Clique em **Sim**.
    
3. Usando a instalação inteligente, um novo recurso no Skype for Business Server, você pode se conectar à Internet para verificar se há atualizações durante o processo de instalação. Isso oferece uma experiência melhor, garantindo que você tenha as atualizações mais recentes para o produto na instalação. Clique em **Instalar** para iniciar a instalação.
    
4. Revise cuidadosamente o contrato de licença e, se concordar, selecione **aceito os termos do contrato de licença**e clique em **OK**.
    
5. Os componentes principais do Skype for Business Server serão instalados no servidor. 
    
    Os componentes principais consistem nos seguintes, conforme mostrado na figura.
    
    ![Principais componentes na tela aplicativos.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Assistente de implantação do Skype for Business Server** Um programa de implantação que fornece um bloco de inicialização para instalar os vários componentes do Skype for Business Server.
    
   - **Shell de gerenciamento do Skype for Business Server** Um programa pré-configurado do PowerShell que permite a administração do Skype for Business Server.
    
     Depois que a instalação dos componentes principais estiver concluída, o assistente de implantação do Skype for Business Server será iniciado automaticamente, conforme mostrado na figura. 
    
     ![Assistente de implantação do Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Além dos componentes principais, você também precisará instalar o construtor de topologias do Skype for Business Server e o painel de controle do Skype for Business Server em pelo menos um servidor no ambiente. Clique em **instalar ferramentas administrativas** no assistente de implantação.
    
7. Clique em **Avançar** para iniciar a instalação.
    
8. Depois que a instalação for concluída, clique em **concluir**. As ferramentas administrativas agora são adicionadas ao servidor, conforme mostrado na figura.
    
    ![Ferramentas administrativas do Skype for Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Construtor de topologia do Skype for Business Server** Um programa usado para compilar, implantar e gerenciar topologias.
    
   - **Painel de controle do Skype for Business Server** Um programa usado para administrar a instalação.
    

