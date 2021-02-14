---
title: Criar um compartilhamento de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: saiba como criar um compartilhamento de arquivos do Windows Server como parte da instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812231"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Criar um compartilhamento de arquivos no Skype for Business Server
 
**Resumo:** Saiba como criar um compartilhamento de arquivos do Windows Server como parte da instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
O Skype for Business Server requer um compartilhamento de arquivos para que os computadores em toda a topologia possam trocar arquivos. Criar um compartilhamento de arquivos é a etapa 2 de 8 no processo de instalação do Skype for Business Server. Você pode realizar as etapas 1 a 5 em qualquer ordem. No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas 1 a 5, conforme descrito no diagrama. Para detalhes de planejamento sobre compartilhamento de arquivos, consulte [Requisitos](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) de ambiente para Skype for Business Server ou requisitos de servidor [para o Skype for Business Server 2019.](../../../SfBServer2019/plan/system-requirements.md)
  
![Diagrama de visão geral](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivos básico

Esta seção orienta você na criação de um compartilhamento de arquivos básico do Windows Server. Um compartilhamento de arquivos básico do Windows Server é suportado com o Skype for Business Server. No entanto, ele não fornece explicitamente alta disponibilidade. Para um ambiente de alta disponibilidade, recomenda-se um compartilhamento de arquivos DFS (Sistema de Arquivos Distribuído). Para obter mais informações sobre um compartilhamento de arquivos de alta disponibilidade e DFS, consulte Plano para alta disponibilidade e recuperação de desastres [no Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> O Windows Server 2012 R2 fez grandes saltos no fornecimento de soluções de compartilhamento de arquivos como SAN (Rede de Área de Armazenamento) usando a plataforma do Windows Server. Quando comparada a um dispositivo baseado em SAN tradicional, uma solução de armazenamento do Windows Server 2012 R2 pode cortar custos pela metade com muito impacto mínimo sobre o desempenho. Para obter mais informações sobre opções de compartilhamento de arquivos no Windows Server 2012 R2, consulte o white paper baixável [Windows Server 2012 R2 Storage.](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf) 
  
Assista às etapas de vídeo **para criar um compartilhamento de arquivos:**
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Criar um compartilhamento de arquivos básico

1. Faça logoff no computador que hospedará o compartilhamento de arquivos.
    
2. Clique com o botão direito do mouse na pasta que você planeja compartilhar e selecione **Propriedades.**
    
3. Selecione a **guia Compartilhamento** e clique em **Compartilhamento Avançado.**
    
4. Clique **em Compartilhar esta pasta.**
    
5. Clique em **Permissões**.
    
6. Adicione o grupo de **Administradores** local do servidor que hospeda o compartilhamento de arquivos, conceda a Eles os direitos Permitir: Controle **Total,** Alterar e Leitura e clique em **OK.**
    
7. Clique **em OK** novamente e anote o caminho da rede.
    
8. Clique **em Feito** para fechar o assistente.
    
     ![Guia de compartilhamento para compartilhar uma pasta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Se o armazenamento de arquivos estiver hospedado em um compartilhamento DFS, o seguinte aviso será recebido:

Aviso: Não é possível acessar permissões de compartilhamento para " \\ <domain> \<share> ".

>Isso é esperado se você não for um administrador no servidor de arquivos ou se for um compartilhamento dfs (sistema de arquivos distribuídos). Se as permissões de compartilhamento já foram configuradas, esse aviso pode ser ignorado. Se for um novo compartilhamento, consulte a documentação para obter detalhes sobre como configurar manualmente as permissões de compartilhamento.

>Devido à incapacidade de acessar as permissões de compartilhamento em um compartilhamento DFS, o Skype for Business Server não poderá definir explicitamente grupos no compartilhamento de arquivos. Para garantir que os componentes do Skype for Business Server possam acessar o compartilhamento de arquivos com as permissões apropriadas, verifique se os seguintes grupos RTC foram adicionados com permissões de compartilhamento de nível de Leitura e Alteração, além dos Administradores locais com permissões de compartilhamento controle total.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
