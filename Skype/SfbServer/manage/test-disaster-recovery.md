---
title: Teste de recuperação de desastre no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Executar uma recuperação do sistema para um servidor do pool do servidor do Skype for Business para testar o processo de recuperação de desastres documentado
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279211"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Teste de recuperação de desastre no Skype for Business Server

Realize uma recuperação do sistema para um servidor do pool do servidor do Skype for Business para testar o processo de recuperação de desastres documentado. Esse teste simulará uma falha de hardware completa para um servidor e ajudará a garantir que os recursos, planos e dados estejam disponíveis para recuperação. Tente alternar o foco do teste mensalmente para que sua organização teste sempre a falha de um servidor diferente ou de outro equipamento. 

Observe que o cronograma de execução do teste de Recuperação de Desastre pelas organizações variará. É muito importante que o teste de recuperação de desastre não seja ignorado ou negligenciado. 

Exportar a topologia, as políticas e as configurações de configuração do Skype for Business Server para um arquivo. O arquivo poderá ser usado, entre outras coisas, para restaurar essas informações para o Repositório de Gerenciamento Central após uma atualização, uma falha de hardware ou outro problema que resulte em perda de dados.

Importe as configurações de topologia, políticas e configuração do Skype for Business Server para o repositório de gerenciamento central ou para o computador local, conforme mostrado nos seguintes comandos: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Para fazer backup de dados de produção:

- Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup padrão do SQL Server para despejar o banco de dados em um dispositivo de despejo de arquivo ou fita.
- Use um aplicativo de backup terceirizado para fazer backup dos dados para um arquivo ou uma fita.
- Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.
- Use o backup do sistema de arquivos ou backup de terceiros para fazer backup de conteúdo da reunião e registros de conformidade.
- Use a ferramenta de linha de comando Export-CsConfiguration para fazer backup das configurações do Skype for Business Server.

A primeira etapa do procedimento de failover inclui um movimento forçado dos usuários do pool de produção para o pool de Recuperação de Desastre. O movimento será forçado, pois o pool de produção não estará disponível para aceitar a realocação do usuário.

O processo de mudança de usuário do Skype for Business Server é efetivamente uma mudança para um atributo no objeto da conta de usuário, além de uma atualização de registro no banco de dados SQL do RTC. Esses dados podem ser restaurados do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server ou usando um utilitário de backup/restauração de terceiros.

Depois que esses dados são restaurados, os usuários podem conectar-se efetivamente ao pool de recuperação de desastres e operar normalmente. Para permitir que os usuários se conectem ao pool de recuperação de desastre, uma alteração de registro DNS será necessária.

O pool de produção do Skype for Business será referenciado por clientes que usam os registros de configuração automática e SRV DNS de:

- SRV: _sip. _tls. \<domain>/CNAME: SIP. \<domain>
- CNAME: SIP. \<domain>/CVC-pool-1. \<domain>

Para facilitar o failover, esse registro CNAME deve ser atualizado para referenciar o FQDN DROCSPool:

- CNAME: SIP.<domain> /DROCSPool. \<domain>
- SPI. \<domain>
- AV.\<domain>
- webconf. \<domain>
