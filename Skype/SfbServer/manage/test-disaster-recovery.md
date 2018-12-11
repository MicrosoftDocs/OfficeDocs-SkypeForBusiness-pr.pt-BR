---
title: Recuperação de desastres testes no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Executar uma recuperação do sistema para um Skype para o pool de servidores Business Server testar seu processo de recuperação de desastres documentadas
ms.openlocfilehash: d401d27c1cc0f5b04c6e256a1e55f6847c9c35ba
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222720"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Recuperação de desastres testes no Skype para Business Server

Execute uma recuperação do sistema para um Skype para o pool de servidores Business Server testar seu processo de recuperação de desastres documentadas. Esse teste será simular uma falha completa de hardware para um servidor e ajudará a garantir que os recursos, os planos e os dados estão disponíveis para a recuperação. Tente alternar o foco do teste mensalmente para que sua organização teste sempre a falha de um servidor diferente ou de outro equipamento. 

Observe que o cronograma de execução do teste de Recuperação de Desastre pelas organizações variará. É muito importante que o teste de recuperação de desastre não seja ignorado ou negligenciado. 

Exporte seu Skype para Business Server topologia, políticas e definições de configuração para um arquivo. O arquivo poderá ser usado, entre outras coisas, para restaurar essas informações para o Repositório de Gerenciamento Central após uma atualização, uma falha de hardware ou outro problema que resulte em perda de dados.

Importe sua Skype para topologia de servidor de negócios, políticas e definições de configuração para o repositório de gerenciamento Central ou no computador local, conforme mostrado nos comandos a seguir: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para fazer backup dos dados de produção:

- Fazer backup de bancos de dados RTC e LCSLog usando o SQL Server standard backup processo para o banco de dados para um dispositivo de despejo fita ou arquivo de despejo.
- Use um aplicativo de backup terceirizado para fazer backup dos dados para um arquivo ou uma fita.
- Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.
- Use o backup do sistema de arquivos ou o backup de terceiros para fazer backup de logs de conteúdo e de conformidade da reunião.
- Use a ferramenta de linha de comando de Export-CsConfiguration para fazer o backup Skype pelas configurações do servidor de negócios.

A primeira etapa do procedimento de failover inclui um movimento forçado dos usuários do pool de produção para o pool de Recuperação de Desastre. O movimento será forçado, pois o pool de produção não estará disponível para aceitar a realocação do usuário.

O Skype para o processo de movimentação de Business Server do usuário é efetivamente uma alteração em um atributo no objeto de conta de usuário, além de uma atualização de registro no banco de dados RTC SQL. Esses dados podem ser restaurados do dispositivo despejo backup original da produção do SQL Server usando o processo de restauração do SQL Server standard, ou usando um terceiro backup/restauração utilitário.

Depois que esses dados for restaurados, os usuários efetivamente podem conectar ao pool de recuperação de desastres e operar como de costume. Para permitir que os usuários se conectem ao pool de recuperação de desastres, uma alteração de registro de DNS será necessária.

A produção Skype para pool de negócios será referenciada pelos clientes estão usando a configuração automática e registros SRV de DNS:

- SRV: _sip._tls. \<domínio > /CNAME: SIP. \<domínio >
- CNAME: SIP. \<domínio > /cvc-pool-1. \<domínio >

Para facilitar o failover, esse registro CNAME deve ser atualizado para referenciar o FQDN DROCSPool:

- CNAME: SIP.<domain> / DROCSPool. \<domínio >
- SIP. \<domínio >
- Antivírus.\<domínio >
- webconf. \<domínio >
