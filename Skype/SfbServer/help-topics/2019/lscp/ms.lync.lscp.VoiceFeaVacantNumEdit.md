---
title: Número de telefone não atribuído criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 87d83f6285e36abf6b063ba7d6c4d1a93cadc633
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792159"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de Telefone Não Atribuído: Criar Novo ou Editar Existente

> [!NOTE]
> O Exchange UM permanecerá disponível no Skype for Business Server 2019 quando você integrar o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016. Devido a alterações no suporte ao Exchange 2019, a integração de UM Exchange está sendo realçada em favor do recurso de correio de voz e do atendedor automático na nuvem.

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

Para obter detalhes sobre recursos e recursos do lançamento, consulte [planejar o aplicativo de anúncio no Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação de planejamento. Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte  [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação Operações.


