---
title: Crie um compartilhamento de arquivo no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumo: Saiba como criar um compartilhamento de arquivo do Windows Server como parte da instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a84e37c3d069c3f51570b600d5ec4804d2a5ee3c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967111"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Crie um compartilhamento de arquivo no Skype para Business Server
 
**Resumo:** Saiba como criar um compartilhamento de arquivo do Windows Server como parte da instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype para Business Server requer um compartilhamento de arquivos, para que os computadores em toda a topologia podem trocar arquivos. Criação de um compartilhamento de arquivo é a etapa 2 de 8 no processo de instalação de Skype para Business Server. As etapas 1 a 5 podem ser executadas em qualquer ordem. No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. Para detalhes sobre compartilhamento de arquivos de planejamento, consulte [requisitos de ambiente para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagrama de visão geral](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivo básico

Esta seção ajuda você a criar um compartilhamento de arquivos básico no Windows Server. Um compartilhamento de arquivos básico do Windows Server é compatível com Skype para Business Server. No entanto, ele não explicitamente oferece alta disponibilidade. Para um ambiente de alta disponibilidade, recomenda-se um compartilhamento de arquivo de sistema de arquivos distribuído (DFS). Para obter mais informações sobre um compartilhamento de arquivos de alta disponibilidade e o DFS, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> O Windows Server 2012 R2 deu grandes saltos no fornecimento de soluções de compartilhamento similares à rede SAN usando a plataforma do Windows Server. Quando comparada a um aplicativo baseado em uma rede SAN tradicional, uma solução de armazenamento do Windows Server 2012 R2 pode cortar custos pela metade, com mínimo impacto sobre o desempenho. Para obter mais informações sobre as opções de compartilhamento de arquivo no Windows Server 2012 R2, consulte o white paper baixável [O armazenamento do Windows Server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Assista as etapas do vídeo para **criar um compartilhamento de arquivos**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivo básico

1. Faça logon no computador que hospedará o compartilhamento de arquivo.
    
2. Clique com botão direito na pasta que você planeja compartilhar e selecione **Propriedades**.
    
3. Selecione a guia **Compartilhamento** e clique em **Compartilhamento Avançado**.
    
4. Clique em **Compartilhar esta pasta**.
    
5. Clique em **Permissões**.
    
6. Adicione o **grupo local de administradores** do servidor que está hospedando o compartilhamento de arquivos, concedendo **Permitir: Todos os direitos de Controle, Alteração e Leitura** e clique em **OK**.
    
7. Clique em **OK** novamente e tome nota do caminho da rede.
    
8. Clique em **Concluído** para fechar o assistente.
    
     ![Guia de compartilhamento para compartilhar uma pasta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

