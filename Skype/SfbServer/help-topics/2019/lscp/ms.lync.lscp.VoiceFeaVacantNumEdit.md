---
title: Número não atribuído Telefone Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: fb9542cb48fbcbda2bba42a2d691e26030edc9dd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606520"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de Telefone Não Atribuído: Criar Novo ou Editar Existente

> [!NOTE]
> Exchange A UM permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com Exchange 2013 ou Exchange 2016. Devido às alterações no suporte no Exchange 2019, Exchange integração de UM está sendo desalmada em favor dos recursos Caixa postal na Nuvem e Cloud Atendedor Automático.

Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.

> [!IMPORTANT]
> Depois de concluir a criação de um novo intervalo de números não atribuídos ou editar um intervalo existente, clique em **OK** para retornar à página **Número Não Atribuído** que lista todos os intervalos de número. As alterações feitas na página **Novo Intervalo de Números Não Atribuídos** ou na página **Editar Intervalo de Números Não Atribuídos** não são confirmadas no banco de dados até que você clique em **Confirmar tudo** na página **Número Não Atribuído**.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Digite um nome descritivo que identifica o intervalo de números não atribuídos. Depois de salvar o intervalo, esse nome não pode ser alterado.

- **Intervalo de números** No primeiro campo, digite o número inicial do intervalo de números não atribuídos. No segundo campo, digite o número final do intervalo.

  - O número inicial do intervalo precisa ser menor ou igual ao número final do intervalo.

  - Se o número inicial do intervalo ou o número final do intervalo incluir um número de extensão, os números inicial e final do intervalo precisarão incluir uma extensão e o número de extensão deverá ser o mesmo para os números inicial e final.

  - O número deve corresponder à expressão regular ( `tel:` )?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. Isso significa que o número pode começar com a cadeia de caracteres 'tel:'. Se você não especificar essa cadeia de caracteres, ela será adicionada automaticamente para você, como um sinal de a mais (+) e um dígito de 1 a 9. O número de telefone pode ter até 17 dígitos e pode ser seguido por uma extensão no formato ;ext= seguido pelo número de extensão.

- **Serviço de comunicado** Selecione **Comunicado** para que o aplicativo Comunicado manipular a chamada de entrada ou Exchange UM para ter um Exchange **de** UM Atendedor Automático lidar com a chamada de entrada.

- Se você tiver selecionado **Anúncio** para **Serviço de anúncio**:

  - **FQDN do servidor de destino** Selecione a ID de serviço do serviço application que executa o aplicativo Comunicado que tratará de chamadas de entrada para esse intervalo de números não atribuídos.

  - **Comunicado** Selecione o comunicado a ser tocado para esse intervalo de números não atribuídos.

- Se você tiver selecionado **U do Exchange** para **Serviço de anúncio**:

  - **Atendedor Automático telefone** Selecione o número de telefone do Exchange um Atendedor Automático.

Para obter detalhes sobre recursos e recursos do Comunicado, consulte [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação Planejamento. Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) na documentação Operações.