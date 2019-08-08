---
title: Criar um compartilhamento de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumo: saiba como criar um compartilhamento de arquivos do Windows Server como parte da instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 3f539d980d2978ee3be5e8249f869aa234493f32
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235239"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Criar um compartilhamento de arquivos no Skype for Business Server
 
**Resumo:** Saiba como criar um compartilhamento de arquivos do Windows Server como parte da instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
O Skype for Business Server exige um compartilhamento de arquivos para que os computadores em toda a topologia possam trocar arquivos. A criação de um compartilhamento de arquivos é a etapa 2 de 8 no processo de instalação do Skype for Business Server. Você pode executar os passos 1 a 5 em qualquer ordem. No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. Para obter detalhes sobre o compartilhamento de arquivos, consulte [requisitos ambientais para](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) requisitos do servidor ou do Skype for Business Server [para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagrama de visão geral](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivo básico

Esta seção ajuda você a criar um compartilhamento de arquivos básico no Windows Server. Um compartilhamento de arquivos básico do Windows Server é compatível com o Skype for Business Server. No entanto, ele não fornece explicitamente alta disponibilidade. Para um ambiente de alta disponibilidade, recomenda-se um compartilhamento de arquivo de sistema de arquivos distribuído (DFS). Para obter mais informações sobre um compartilhamento de arquivos de alta disponibilidade e DFS, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> O Windows Server 2012 R2 deu grandes saltos no fornecimento de soluções de compartilhamento similares à rede SAN usando a plataforma do Windows Server. Quando comparada a um aplicativo baseado em uma rede SAN tradicional, uma solução de armazenamento do Windows Server 2012 R2 pode cortar custos pela metade, com mínimo impacto sobre o desempenho. Para obter mais informações sobre as opções de compartilhamento de arquivos no Windows Server 2012 R2, consulte o artigo disponível para download em inglês do [Windows server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
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
    
     ![Guia compartilhamento para compartilhar uma pasta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Se o repositório de arquivos estiver hospedado em um compartilhamento DFS, o seguinte aviso será recebido:

Aviso: não é possível acessar as permissões de\\<domain>\<compartilhamento para "compartilhar>".

>Isso é esperado se você não for um administrador no servidor de arquivos ou se for um compartilhamento DFS (Distributed File System). Se as permissões de compartilhamento já tiverem sido configuradas, esse aviso pode ser ignorado. Se for um novo compartilhamento, consulte a documentação para obter detalhes sobre como configurar manualmente as permissões de compartilhamento.

>Devido à incapacidade de acessar as permissões de compartilhamento em um compartilhamento DFS, o Skype for Business Server não poderá definir grupos explicitamente no compartilhamento de arquivos. Para garantir que os componentes do Skype for Business possam acessar o compartilhamento de arquivos com as permissões apropriadas, certifique-se de que os seguintes grupos RTC sejam adicionados com permissões de compartilhamento de nível de alteração, além dos administradores locais, com permissões de compartilhamento de controle total.

RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins
