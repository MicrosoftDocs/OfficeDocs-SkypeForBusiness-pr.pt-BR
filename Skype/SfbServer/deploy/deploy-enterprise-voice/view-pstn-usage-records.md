---
title: Exibir registros de uso de PSTN em Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumo: saiba como exibir registros de uso PSTN usando o Painel de Controle Skype for Business Server ou o Shell de Gerenciamento Skype for Business Server.'
ms.openlocfilehash: 7b708a388950424453e833c28d846e6258070ef5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626183"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Exibir registros de uso de PSTN em Skype for Business

**Resumo:** Saiba como exibir registros de uso de PSTN usando o Painel de Controle Skype for Business Server ou o Shell de Gerenciamento Skype for Business Server.

Um registro de uso PSTN (Rede Telefônica Pública Comutado) especifica uma classe de chamada (como interna, local ou longa distância) que pode ser feita por vários usuários ou grupos de usuários em uma organização. Para obter detalhes, consulte [Registros de Uso PSTN](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) na documentação planejamento.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Para exibir um registro de uso PSTN usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação esquerda, clique em **Roteamento** de Voz e clique em **Uso PSTN.**

3. Na página **Uso PSTN,** realça o registro de uso PSTN que você deseja exibir, clique em **Editar** e clique em **Mostrar detalhes**.

    > [!NOTE]
    > Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Para exibir as informações de uso do PSTN usando Skype for Business Server cmdlets do Shell de Gerenciamento

- Para exibir informações sobre todos os seus usos PSTN, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:

  ```powershell
  Get-CsPstnUsage
  ```

    Esse comando retornará informações parecidas com:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Confira também

[Criar ou modificar uma política de voz e configurar registros de uso PSTN em Skype for Business](voice-policy-and-pstn-usage-records.md)