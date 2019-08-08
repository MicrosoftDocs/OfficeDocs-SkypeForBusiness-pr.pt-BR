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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumo: saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 168202048fcd72b16d93cfd410f678cad01b3058
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244617"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalar ferramentas administrativas no Skype for Business Server
 
**Resumo:** Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
As ferramentas administrativas incluem o Construtor de Topologias e o Painel de Controle. As ferramentas administrativas devem ser instaladas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 executando uma versão do sistema operacional do Windows que seja compatível com o Skype for Business Server. Você pode executar os passos 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. A instalação das ferramentas administrativas é a etapa 3 de 8.
  
![Diagrama de visão geral](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instalar as ferramentas administrativas do Skype for Business Server

A mídia de instalação do Skype for Business Server oferece uma experiência flexível. Quando você executa o setup. exe pela primeira vez, as únicas ferramentas instaladas são o assistente de implantação do Skype for Business Server e o Shell de gerenciamento do Skype for Business Server. Ao usar essas duas ferramentas, conhecida como componentes principais, você pode continuar com o processo de instalação, mas elas não oferecem a funcionalidade principal para o ambiente geral do Skype for Business Server. O Assistente de Implantação é iniciado automaticamente após a instalação dos Componentes Básicos. A seção do assistente de implantação intitulado **instalar ferramentas administrativas** instala o construtor de topologias do Skype for Business Server e o painel de controle do Skype for Business Server.
  
> [!IMPORTANT]
> Cada ambiente do Skype for Business Server deve ter pelo menos um servidor com as ferramentas administrativas instaladas. 
  
Veja as etapas do vídeo para **instalar ferramentas administrativas**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instalar as ferramentas administrativas do Skype for Business Server pelo assistente de implantação

1. Insira a mídia de instalação do Skype for Business Server. Se a instalação não começar automaticamente, clique duas vezes em **Instalar**.
    
2. A mídia de instalação requer o Microsoft Visual C++ para ser executada. Uma caixa de diálogo aparecerá perguntando se você quer instalá-lo. Clique em **Sim**.
    
3. Ao usar a configuração inteligente, um novo recurso no Skype for Business Server, você pode se conectar à Internet para verificar se há atualizações durante o processo de instalação. Este recurso proporciona uma experiência aprimorada ao assegurar que você tenha as atualizações mais recentes do produto. Clique em **Instalar** para começar a instalação.
    
4. Leia com atenção o Contrato de Licença e se você estiver de acordo, selecione **Aceito os termos do contrato de licença** e clique em **OK**.
    
5. Os componentes principais do Skype for Business Server serão instalados no servidor. 
    
    Os Componentes consistem nos itens a seguir, como mostra a figura.
    
    ![Componentes Principais na tela de aplicativos.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Assistente de implantação do Skype for Business Server** Um programa de implantação que fornece um bloco de inicialização para a instalação de vários componentes do Skype for Business Server.
    
   - **Shell de gerenciamento do Skype for Business Server** Um programa pré-configurado do PowerShell que permite a administração do Skype for Business Server.
    
     Após a conclusão da instalação dos componentes principais, o assistente de implantação do Skype for Business Server será iniciado automaticamente, conforme mostrado na figura. 
    
     ![Assistente de Implantação do Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Além dos componentes centrais, você também precisará instalar o construtor de topologias do Skype for Business Server e o painel de controle do Skype for Business Server em pelo menos um servidor no ambiente. Clique em **Instalar ferramentas administrativas** no Assistente de Implantação.
    
7. Clique em **Avançar** para começar a instalação.
    
8. Assim que a instalação for concluída, clique em **Concluir**. As ferramentas administrativas agora são adicionadas ao servidor, conforme mostra a figura.
    
    ![Ferramentas administrativas do Skype for Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Construtor de topologias do Skype for Business Server** Um programa usado para compilar, implantar e gerenciar topologias.
    
   - **Painel de controle do Skype for Business Server** Um programa usado para administrar a instalação.
    

