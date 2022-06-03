---
title: Criar um compartilhamento de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumo: saiba como criar um compartilhamento de arquivos Windows Server como parte da instalação do Skype for Business Server.'
ms.openlocfilehash: 12ea75a11470d5730c891b1c738a3337ccb28ac8
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860722"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Criar um compartilhamento de arquivos no Skype for Business Server
 
**Resumo:** Saiba como criar um compartilhamento de arquivos Windows Server como parte da instalação do Skype for Business Server.
  
Skype for Business Server requer um compartilhamento de arquivos para que os computadores em toda a topologia possam trocar arquivos. A criação de um compartilhamento de arquivos é a etapa 2 de 8 no processo de instalação para Skype for Business Server. Você pode executar as etapas de 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. Para obter detalhes de planejamento sobre o compartilhamento de arquivos, consulte [Requisitos ambientais para Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagrama de visão geral.](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivos básico

Esta seção explica como criar um compartilhamento de arquivos Windows Server básico. Um compartilhamento de Windows Server básico é compatível com Skype for Business Server. No entanto, ele não fornece explicitamente alta disponibilidade. Para um ambiente de alta disponibilidade, é recomendável um compartilhamento de arquivos DFS (Sistema de Arquivos Distribuído). Para obter mais informações sobre um compartilhamento de arquivos de alta disponibilidade e DFS, consulte Planejar alta disponibilidade e recuperação de desastre [Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 fez grandes saltos ao fornecer soluções de compartilhamento de arquivos semelhantes Armazenamento SAN (rede de área) usando a plataforma Windows Server. Quando comparado a um dispositivo tradicional baseado em SAN, uma solução de armazenamento Windows Server 2012 R2 pode reduzir os custos pela metade com impacto muito mínimo no desempenho. Para obter mais informações sobre as opções de compartilhamento de arquivos no Windows Server 2012 R2, consulte o white paper para download [Windows Server 2012 R2 Armazenamento](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Assista às etapas de vídeo para **criar um compartilhamento de arquivos**:
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivos básico

1. Faça logon no computador que hospedará o compartilhamento de arquivos.
    
2. Clique com o botão direito do mouse na pasta que você planeja compartilhar e selecione **Propriedades**.
    
3. Selecione a **guia** Compartilhamento e clique em **Compartilhamento Avançado**.
    
4. Clique **em Compartilhar esta pasta**.
    
5. Clique em **Permissões**.
    
6. Adicione o grupo **local administradores** do servidor que hospeda o compartilhamento de arquivos, conceda permissão: controle total **,** alteração e direitos de leitura e clique em **OK**.
    
7. Clique **em OK** novamente e anote o caminho da rede.
    
8. Clique **em Concluído** para fechar o assistente.
    
     ![Guia Compartilhamento para compartilhar uma pasta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Se o repositório de arquivos estiver hospedado em um compartilhamento DFS, o seguinte aviso será recebido:

`Warning: Unable to access share permissions for "\\<domain>\<share>".`

>Isso é esperado se você não for um administrador no servidor de arquivos ou se for um compartilhamento do DFS (Sistema de Arquivos Distribuído). Se as permissões de compartilhamento já tiverem sido configuradas, esse aviso poderá ser ignorado. Se for um novo compartilhamento, consulte a documentação para obter detalhes sobre como configurar manualmente as permissões de compartilhamento.

>Devido à incapacidade de acessar as permissões de compartilhamento em um compartilhamento dfs, Skype for Business Server poderá definir explicitamente grupos no compartilhamento de arquivos. Para garantir que Skype for Business Server componentes possam acessar o compartilhamento de arquivos com as permissões apropriadas, verifique se os seguintes grupos RTC foram adicionados com permissões de compartilhamento no nível de leitura e alteração, além dos Administradores locais com permissões de compartilhamento de Controle Total.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
