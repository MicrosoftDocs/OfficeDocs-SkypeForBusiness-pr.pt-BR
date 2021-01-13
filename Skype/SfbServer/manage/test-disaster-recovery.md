---
title: Teste de recuperação de desastre no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Executar uma recuperação de sistema para um servidor de pool do Skype for Business Server para testar seu processo documentado de recuperação de desastres
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832811"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Teste de recuperação de desastre no Skype for Business Server

Execute uma recuperação de sistema para um servidor de pool do Skype for Business Server para testar seu processo documentado de recuperação de desastres. Esse teste simula uma falha completa de hardware para um servidor e ajudará a garantir que os recursos, planos e dados estão disponíveis para recuperação. Tente girar o foco do teste a cada mês para que sua organização teste a falha de um servidor diferente ou de outro equipamento sempre. 

Observe que o cronograma pelo qual as organizações executam testes de Recuperação de Desastre variará. É muito importante que o teste de recuperação de desastres não seja ignorado ou ignorado. 

Exporte a topologia, as políticas e as definições de configuração do Skype for Business Server para um arquivo. Entre outras coisas, esse arquivo pode ser usado para restaurar essas informações para o Armazenamento de Gerenciamento Central após uma atualização, uma falha de hardware ou algum outro problema que resulte em perda de dados.

Importe sua topologia, políticas e definições de configuração do Skype for Business Server para o armazenamento de Gerenciamento Central ou para o computador local, conforme mostrado nos seguintes comandos: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para fazer o back up dos dados de produção:

- Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup padrão do SQL Server para despejar o banco de dados em um arquivo ou dispositivo de despejo de fita.
- Use o aplicativo de backup de terceiros para fazer backup dos dados em arquivos ou em fita.
- Use o Export-CsUserData cmdlet para criar uma exportação XML de todo o banco de dados RTC.
- Use o backup do sistema de arquivos ou backup de terceiros para fazer backup do conteúdo da reunião e dos logs de conformidade.
- Use a Export-CsConfiguration de linha de comando para fazer o back up das configurações do Skype for Business Server.

A primeira etapa do procedimento de failover inclui uma movimentação forçada de usuários do pool de produção para o pool de Recuperação de Desastres. Isso será uma movimentação forçada porque o pool de produção não estará disponível para aceitar a realocação do usuário.

O processo de movimentação do usuário do Skype for Business Server é efetivamente uma alteração em um atributo no objeto de conta de usuário, além de uma atualização de registro no banco de dados SQL RTC. Esses dados podem ser restaurados do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server ou usando um utilitário de backup/restauração de terceiros.

Depois que esses dados são restaurados, os usuários podem se conectar efetivamente ao pool de Recuperação de Desastres e operar normalmente. Para permitir que os usuários se conectem ao pool de Recuperação de Desastres, uma alteração de registro DNS será necessária.

O pool de produção do Skype for Business será referenciado pelos clientes usando a configuração automática e os registros SRV DNS de:

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Para facilitar o failover, esse registro CNAME deve ser atualizado para fazer referência ao FQDN DROCSPool:

- CNAME: SIP.<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- AV.\<domain>
- webconf.\<domain>
