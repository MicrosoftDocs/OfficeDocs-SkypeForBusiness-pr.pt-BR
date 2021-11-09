---
title: Configurar o armazenamento de contatos pessoais em computadores cliente do Lync 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumo: configure o armazenamento de contatos pessoal usado por clientes herdados.'
ms.openlocfilehash: de9bc9472f619f7d35bbc4585d806f6cd82c295a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842363"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurar o armazenamento de contatos pessoais em computadores cliente do Lync 2010
  
Se você estiver integrando o Skype for Business Server 2015 e Exchange Server 2016 ou Exchange Server 2013, configure o armazenamento de contatos pessoal usado pelos clientes. Em particular, você deve configurar Skype for Business usar o Exchange como o armazenamento de contatos pessoais e, ao mesmo tempo, garantir que os usuários não sejam capazes de substituir essa decisão. Isso pode ser feito criando e configurando um valor do Registro em cada computador cliente.
  
> [!NOTE]
> O procedimento a seguir só é necessário para clientes que usam o cliente Lync 2010 ou anterior. O cliente do Lync 2013 e todos os clientes Skype for Business não terão a opção de substituindo as configurações do armazenamento de contatos.
  
Para configurar esse valor em um único computador, execute os seguinte procedimento:
  
1. No computador cliente, clique em **Iniciar** e clique em **Executar**.
2. Na caixa **de diálogo** Executar, digite regedit e pressione ENTER.
3. No Editor de Registro, **expanda HKEY_LOCAL_MACHINE,** expanda **Software,** expanda **Políticas,** **expanda a Microsoft** e **expanda Communicator**.
4. Clique com o **Communicator,** aponte para **Novo** e clique em **Valor DWORD (32 bits).**
5. Após a criação do novo valor, digite PersonalContactStoreOverride e pressione ENTER para renomear o valor.
6. Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.

Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo. Para obter detalhes sobre como fazer isso Windows 10, consulte [o artigo Criar um objeto de política de grupo.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
