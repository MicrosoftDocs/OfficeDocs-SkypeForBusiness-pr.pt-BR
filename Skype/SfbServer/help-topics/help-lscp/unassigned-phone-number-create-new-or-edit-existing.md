---
title: Número de telefone não atribuído criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: e8a294273591969430abbbc450a37a5292fbe0c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685664"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de Telefone Não Atribuído: Criar Novo ou Editar Existente

Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.

> [!IMPORTANT]
> Quando terminar de criar um novo intervalo de números não atribuídos ou editar um existente, clique em **OK** para retornar à página de **número não atribuído** que lista todos os intervalos de números. As alterações feitas na página **nova faixa de número não atribuída** ou **Editar número não atribuído da Rage** não são confirmadas para o banco de dados até que você clique em **confirmar tudo** na página **número não atribuído** .

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Digite um nome descritivo que identifique o intervalo numérico não atribuído. Depois de salvar o intervalo, esse nome não poderá ser alterado.

- **Intervalo de números** No primeiro campo, digite o número inicial do intervalo numérico não atribuído. No segundo campo, digite o número final do intervalo.

  - O número inicial do intervalo deve ser menor ou igual ao número final.

  - Se o número inicial ou o número final do intervalo incluir um número de ramal, ambos os números devem incluir um ramal, que deve ser o mesmo para ambos.

  - O número deve corresponder à expressão regular (Tel:)? ( \+)? [1-9] \d{0,17}(; Ext = [1-9] \d{0,9})?. Isso significa que o número pode começar com a cadeia de caracteres Tel: (se você não especificar essa cadeia de caracteres, ela será adicionada automaticamente para você), um sinal de adição (+) e um dígito de 1 a 9. O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext= seguido do número do ramal.

- **Serviço de anúncio** Selecione **anúncio** para que o aplicativo de anúncio manipule a chamada de entrada ou o **Exchange um** para que um atendedor automático de um Exchange trate a chamada de entrada.

- Se você selecionou **anúncio** para **serviço de anúncio**:

  - **FQDN do servidor de destino** Selecione a ID de serviço do serviço de aplicativo que executa o aplicativo de anúncio que manipulará as chamadas de entrada para essa faixa de números não atribuídos.

  - **Aviso** Selecione o aviso a ser reproduzido para esse intervalo de números não atribuídos.

- Se você selecionou o **Exchange um** para o **serviço de anúncio**:

  - **Número de telefone do atendedor automático** Selecione o número de telefone para o atendedor automático de UM do Exchange.

Para obter detalhes sobre os recursos e funções do Comunicado, confira [Planejar o aplicativo Comunicado no Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação de Planejamento. Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte  [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação Operações.


