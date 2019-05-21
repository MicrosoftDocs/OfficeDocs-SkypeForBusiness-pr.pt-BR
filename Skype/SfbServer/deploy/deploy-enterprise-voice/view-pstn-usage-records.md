---
title: Exibir registros de uso de PSTN no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumo: saiba como exibir registros de uso de PSTN usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server.'
ms.openlocfilehash: d00fcab8c7f5ad9b8f47d5aecb6c6169e8d43574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300920"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Exibir registros de uso de PSTN no Skype for Business

**Resumo:** Saiba como exibir registros de uso de PSTN usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server.

Um registro de uso de Rede Telefônica Pública Comutada (PSTN) especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização. Para obter detalhes, consulte [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) na documentação de planejamento.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para exibir um registro de uso PSTN usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Roteamento de voz** e em **Uso do PSTN**.

3. Na página **Uso do PSTN**, destaque o registro de uso PSTN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes**.

    > [!NOTE]
    > Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para exibir informações de uso de PSTN usando cmdlets do Shell de gerenciamento do Skype for Business Server

- Para ver informações sobre todos os usos de PSTN, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:

  ```
  Get-CsPstnUsage
  ```

    Este comando retorna informações semelhantes para o seguinte:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Confira também

[Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md)

