---
title: Número de telefone não atribuídos criar novo ou editar existente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 3091ae34eee6e877079c927e087789d910d1bf7f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219933"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de Telefone Não Atribuído: Criar Novo ou Editar Existente

Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.

> [!IMPORTANT]
> Quando terminar de criar um novo intervalo de números não atribuído ou editando uma existente, clique em **Okey** para retornar à página de **Número não atribuído** que lista todos os intervalos de números. As alterações feitas na página **Novo Unassigned Number Range** ou a página **Editar moda de número não atribuídos** não são confirmadas no banco de dados até que você clique **em Confirmar tudo** na página **Número não atribuído** .

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Digite um nome descritivo que identifica o intervalo de números não atribuído. Depois de salvar o intervalo, esse nome não pode ser alterado.

- **Intervalo de número** No primeiro campo, digite o número inicial do intervalo de números não atribuído. No segundo campo, digite o número final do intervalo.

  - O número inicial do intervalo deve ser menor ou igual ao número final.

  - Se o número inicial ou o número final do intervalo incluir um número de ramal, ambos os números devem incluir um ramal, que deve ser o mesmo para ambos.

  - Os números devem corresponder à expressão regular (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?. Isso significa que o número pode começar com o cadeia de caracteres tel: (se você não especificar uma cadeia de caracteres ele será automaticamente adicionado para você), um sinal de adição (+) e um dígito entre 1 e 9. O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext= seguido do número do ramal.

- **Serviço de comunicado** Selecione **comunicado** ter o aplicativo de anúncio de lidar com a chamada de entrada ou **UM do Exchange** para ter uma Exchange atendedor automático de UM lidar com a chamada de entrada.

- Se você tiver selecionado **anúncio** para **serviço de anúncio**:

  - **FQDN do servidor de destino** Selecione o ID de serviço do serviço aplicativo que executa o aplicativo de anúncio que lidará com as chamadas de entrada para esse intervalo de números não atribuídos.

  - **Comunicado** Selecione o anúncio a ser reproduzido para esse intervalo de números não atribuídos.

- Se você tiver selecionado **UM do Exchange** para **serviço de anúncio**:

  - **Número de telefone do atendedor automático** Selecione o número de telefone para o Atendedor de automático UM do Exchange.

Para obter detalhes sobre o comunicado recursos e capacidades, consulte o [plano para o aplicativo de anúncio no Skype para negócios 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação de planejamento. Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte  [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação Operações.


