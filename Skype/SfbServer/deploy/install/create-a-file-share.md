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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumo: saiba como criar um compartilhamento de arquivo do Windows Server como parte da instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028292"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Criar um compartilhamento de arquivos no Skype for Business Server
 
**Resumo:** Saiba como criar um compartilhamento de arquivo do Windows Server como parte da instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no centro de avaliação da Microsoft em[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
O Skype for Business Server requer um compartilhamento de arquivos para que os computadores em toda a topologia possam trocar arquivos. A criação de um compartilhamento de arquivos é a etapa 2 de 8 no processo de instalação do Skype for Business Server. Você pode executar as etapas 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 em ordem e depois das etapas 1 a 5, conforme descrito no diagrama. Para obter detalhes de planejamento sobre o compartilhamento de arquivos, consulte [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagrama de visão geral](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivos básico

Esta seção orienta você na criação de um compartilhamento de arquivos básico do Windows Server. Um compartilhamento de arquivos básico do Windows Server é compatível com o Skype for Business Server. No entanto, ele não fornece explicitamente alta disponibilidade. Para um ambiente de alta disponibilidade, é recomendado um compartilhamento de arquivos do sistema de arquivos distribuído (DFS). Para obter mais informações sobre um compartilhamento de arquivos de alta disponibilidade e o DFS, consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> O Windows Server 2012 R2 fez grandes saltos no fornecimento de soluções de compartilhamento de arquivos de rede de área de armazenamento (SAN) usando a plataforma Windows Server. Quando comparado a um dispositivo tradicional baseado em SAN, uma solução de armazenamento do Windows Server 2012 R2 pode cortar custos na metade com impacto muito mínimo sobre o desempenho. Para obter mais informações sobre as opções de compartilhamento de arquivos no Windows Server 2012 R2, consulte o White paper sobre download do [Windows server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Assista as etapas de vídeo para **criar um compartilhamento de arquivos**:
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivos básico

1. Faça logon no computador que hospedará o compartilhamento de arquivos.
    
2. Clique com o botão direito do mouse na pasta que você planeja compartilhar e selecione **Propriedades**.
    
3. Selecione a guia **compartilhamento** e clique em **compartilhamento avançado**.
    
4. Clique em **compartilhar esta pasta**.
    
5. Clique em **Permissões**.
    
6. Adicione o grupo **Administradores** local do servidor que hospeda o compartilhamento de arquivos, conceda **permissões de controle total, alteração e leitura** e clique em **OK**.
    
7. Clique em **OK** novamente e anote o caminho da rede.
    
8. Clique em **concluído** para fechar o assistente.
    
     ![Guia compartilhamento para compartilhar uma pasta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Se o repositório de arquivos estiver hospedado em um compartilhamento DFS, o seguinte aviso será recebido:

Aviso: não é possível acessar as permissões de\\<domain>\<compartilhamento para "compartilhar>".

>Isso é esperado se você não for um administrador no servidor de arquivos ou se for um compartilhamento de sistema de arquivos distribuído (DFS). Se as permissões de compartilhamento já tiverem sido configuradas, este aviso poderá ser ignorado. Se for um novo compartilhamento, consulte a documentação para obter detalhes sobre como configurar manualmente as permissões de compartilhamento.

>Devido à incapacidade de acessar as permissões de compartilhamento em um compartilhamento DFS, o Skype for Business Server não poderá definir grupos explicitamente no compartilhamento de arquivos. Para garantir que os componentes do Skype for Business Server possam acessar o compartilhamento de arquivos com as permissões apropriadas, verifique se os seguintes grupos RTC foram adicionados com permissões de compartilhamento de nível de leitura e alteração, além dos administradores locais com compartilhamento de controle total las.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
