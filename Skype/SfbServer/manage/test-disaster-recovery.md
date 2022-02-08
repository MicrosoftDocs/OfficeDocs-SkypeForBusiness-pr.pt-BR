---
title: Teste de recuperação de desastres em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Executar uma recuperação do sistema para um Skype for Business Server pool para testar seu processo de recuperação de desastre documentado
ms.openlocfilehash: 87b76e958ed35896921791406759e58ce2ee1635
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390103"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Teste de recuperação de desastres em Skype for Business Server

Execute uma recuperação do sistema para um Skype for Business Server pool para testar seu processo de recuperação de desastres documentado. Este teste simula uma falha completa de hardware para um servidor e ajudará a garantir que os recursos, planos e dados estão disponíveis para recuperação. Tente girar o foco do teste a cada mês para que sua organização teste a falha de um servidor diferente ou de outro equipamento sempre. 

Observe que a agenda pela qual as organizações executam testes de Recuperação de Desastres variará. É muito importante que o teste de recuperação de desastres não seja ignorado ou negligenciado. 

Exporte suas Skype for Business Server de topologia, políticas e configurações para um arquivo. Entre outras coisas, esse arquivo pode ser usado para restaurar essas informações para o armazenamento de Gerenciamento Central após uma atualização, uma falha de hardware ou algum outro problema resultou em perda de dados.

Importe suas Skype for Business Server de topologia, políticas e configurações para o armazenamento de Gerenciamento Central ou para o computador local, conforme mostrado nos seguintes comandos: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para fazer o back up de dados de produção:

- Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup de SQL Server padrão para despejar o banco de dados em um dispositivo de despejo de arquivo ou fita.
- Use aplicativo de backup de terceiros para fazer backup dos dados para arquivo ou para fita.
- Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.
- Use o backup do sistema de arquivos ou o backup de terceiros para fazer backup do conteúdo da reunião e dos logs de conformidade.
- Use a Export-CsConfiguration de linha de comando para fazer o Skype for Business Server configurações.

A primeira etapa do procedimento de failover inclui uma movimentação forçada de usuários do pool de produção para o pool de Recuperação de Desastres. Isso será uma movimentação forçada porque o pool de produção não estará disponível para aceitar a realocação do usuário.

O Skype for Business Server processo de movimentação do usuário é efetivamente uma alteração para um atributo no objeto de conta de usuário, além de uma atualização de registro no banco de dados de SQL RTC. Esses dados podem ser restaurados do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração SQL Server padrão ou usando um utilitário de backup/restauração de terceiros.

Depois que esses dados são restaurados, os usuários podem se conectar efetivamente ao pool de Recuperação de Desastres e operar como de costume. Para permitir que os usuários se conectem ao pool de Recuperação de Desastres, será necessária uma alteração de registro DNS.

O pool Skype for Business de produção será referenciado pelos clientes usando a configuração automática e os registros SRV DNS de:

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Para facilitar o failover, esse registro CNAME deve ser atualizado para fazer referência ao FQDN DROCSPool:

- CNAME: SIP.\<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- AV.\<domain>
- webconf.\<domain>
