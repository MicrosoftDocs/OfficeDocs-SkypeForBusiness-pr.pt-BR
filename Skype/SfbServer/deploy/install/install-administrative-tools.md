---
title: Instalar as ferramentas administrativas em Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumo: Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 5f5e00075f34a6a09d36dede7c4cf2ac2a6ab60f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373054"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalar as ferramentas administrativas em Skype para Business Server
 
**Resumo:** Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
As ferramentas administrativas incluem o Construtor de Topologias e o Painel de Controle. As ferramentas administrativas devem ser instaladas em pelo menos um servidor da topologia ou uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional Windows que é suportada para Skype para Business Server. As etapas 1 a 5 podem ser executadas em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. A instalação das ferramentas administrativas é a etapa 3 de 8.
  
![Diagrama de visão geral](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instale o Skype para ferramentas administrativas do servidor de negócios

A mídia de instalação do Skype para Business Server fornece uma experiência flexível. Quando você executa o Setup.exe pela primeira vez, as ferramentas somente instaladas são o Skype para o Assistente de implantação de servidor de negócios e do Skype do Shell de gerenciamento do servidor de negócios. Usando essas duas ferramentas, conhecidas como componentes principais, você pode continuar com o processo de instalação, mas não fornecem funcionalidade principal para o Skype geral para ambiente de servidor de negócios. O Assistente de Implantação é iniciado automaticamente após a instalação dos Componentes Básicos. A seção do Assistente para implantação intitulada **Instalar as ferramentas administrativas** instala Skype para o construtor de topologia de servidor de negócios e Skype para painel de controle do Business Server.
  
> [!IMPORTANT]
> Cada Skype para ambiente de negócios servidor deve ter pelo menos um servidor com as ferramentas administrativas instaladas. 
  
Veja as etapas do vídeo para **instalar ferramentas administrativas**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instale o Skype para ferramentas administrativas do Business Server Assistente de implantação

1. Insira o Skype para a mídia de instalação do servidor de negócios. Se a instalação não começar automaticamente, clique duas vezes em **Instalar**.
    
2. A mídia de instalação requer o Microsoft Visual C++ para ser executada. Uma caixa de diálogo aparecerá perguntando se você quer instalá-lo. Clique em **Sim**.
    
3. Usando a instalação inteligente, um novo recurso do Skype para Business Server, você pode se conectar à Internet para verificar se há atualizações durante o processo de instalação. Este recurso proporciona uma experiência aprimorada ao assegurar que você tenha as atualizações mais recentes do produto. Clique em **Instalar** para começar a instalação.
    
4. Leia com atenção o Contrato de Licença e se você estiver de acordo, selecione **Aceito os termos do contrato de licença** e clique em **OK**.
    
5. O Skype para componentes principais do Business Server será instalado no servidor. 
    
    Os Componentes consistem nos itens a seguir, como mostra a figura.
    
    ![Componentes Principais na tela de aplicativos.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype para o Assistente de implantação de servidor de negócios** Um programa de implantação que fornece um ponto de partida para instalar os vários componentes do Skype para Business Server.
    
   - **Skype do Shell de gerenciamento do servidor de negócios** Um programa PowerShell pré-configurado que permita a administração do Skype para servidores de negócios.
    
     Uma vez concluída a instalação dos componentes principais, o Skype para o Assistente de implantação do Business Server iniciará automaticamente, conforme mostrado na figura. 
    
     ![Assistente de Implantação do Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Além dos componentes principais, você também precisará instalar o Skype para o construtor de topologia de servidor de negócios e Skype para painel de controle do Business Server em pelo menos um servidor no ambiente. Clique em **Instalar ferramentas administrativas** no Assistente de Implantação.
    
7. Clique em **Avançar** para começar a instalação.
    
8. Assim que a instalação for concluída, clique em **Concluir**. As ferramentas administrativas agora são adicionadas ao servidor, conforme mostra a figura.
    
    ![Skype para ferramentas administrativas do servidor de negócios](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype para o construtor de topologia de servidor de negócios** Um programa usado para criar, implantar e gerenciar as topologias.
    
   - **Skype para painel de controle do servidor de negócios** Um programa pode usado para administrar a instalação.
    

