---
title: Instalar pré-requisitos para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumo: saiba mais sobre os servidores e as funções de servidor que você deve configurar antes de instalar Skype for Business Server.'
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860732"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar pré-requisitos para Skype for Business Server
 
**Resumo:** Saiba mais sobre os servidores e as funções de servidor que você deve configurar antes de instalar Skype for Business Server.
  
A instalação de pré-requisitos consiste na configuração do Windows Server instalando as funções e recursos necessários em cada um dos servidores na topologia. Os requisitos são baseados na função que o servidor cumprirá na topologia. Você pode executar as etapas de 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. A instalação de pré-requisitos é a etapa 1 de 8.
  
![Diagrama de visão geral – instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar Windows Server

Skype for Business Server requer o sistema operacional Windows Server e vários pré-requisitos antes que ele possa ser instalado. Para obter detalhes sobre o planejamento de pré-requisitos, consulte [Requisitos do servidor para Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Este procedimento usa Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento poderá ser ligeiramente diferente. 
  
> [!IMPORTANT]
> Antes de começar, verifique se Windows Server está atualizado usando Windows Update. 
  
![Windows servidor atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Assista às etapas de vídeo **para instalar os pré-requisitos**:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar funções e recursos necessários para servidores front-end

Você pode instalar as funções e os recursos necessários usando Gerenciador do Servidor. 
    
1. Instale os recursos de software de pré-requisito listados nos [requisitos do servidor para Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). O software necessário deve estar no servidor que será executado Skype for Business Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 não instala todos os arquivos de origem para os recursos necessários por padrão. Se o servidor não estiver conectado à Internet, você precisará inserir a mídia Windows Server 2012 R2 e selecionar Especificar um caminho de origem alternativo para instalar os recursos necessários. Os arquivos de origem estão localizados no diretório sources\sxs. Por exemplo, se a Windows Server 2012 mídia R2 estiver na unidade D, você definirá o caminho como `d:\sources\sxs`. É importante que você tenha as atualizações mais recentes do Windows Update. Se você não estiver conectado à Internet, precisará instalar manualmente todas as atualizações relevantes, bem como quaisquer pré-requisitos para as atualizações necessárias. 
  
1. Quando a caixa de diálogo indicar que a instalação foi concluída, você precisará reinicializar o servidor para concluir o processo.
    
1. Execute **Windows Update** novamente para verificar se há atualizações nas funções e serviços que foram instalados.
    
1. Se você estiver usando o Skype for Business Server Painel de Controle neste servidor, também deverá instalar o Silverlight. Para instalar o Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Os pré-requisitos para servidores que executam funções diferentes do servidor front-end, como a função de Diretor, Chat Persistente ou Borda, têm seus próprios pré-requisitos. Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte [Os requisitos de servidor para Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

