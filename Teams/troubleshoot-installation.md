---
title: Solucionar problemas de instalação e atualização do Microsoft Teams no Windows
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como solucionar problemas de instalação e atualização do aplicativo cliente do teams na área de trabalho do Windows.
ms.openlocfilehash: f47edf351d6a55f57977fee823d670b749896049
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837621"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Solucionar problemas de instalação e atualização do Microsoft Teams no Windows

Este artigo fornece orientação sobre como diagnosticar e solucionar problemas de instalação e atualização do aplicativo cliente da equipe de trabalho em execução no Windows.

## <a name="check-whether-teams-is-updated-successfully"></a>Verifique se as equipes foram atualizadas com êxito

Siga estas etapas para verificar se uma atualização do teams foi instalada com sucesso.

1. No Teams, selecione a imagem do seu perfil e, em seguida, clique em **sobre** > a**versão**.
2. No mesmo menu, clique em **verificar se há atualizações**.
3. Aguarde a faixa na parte superior do aplicativo para indicar que uma "atualização" do teams é necessária. O link deve ser mostrado a cada minuto mais tarde, pois esse processo faz o download da nova versão do teams. A faixa também permite que você saiba se já está executando a versão mais recente, o que não é necessário atualizar.
4. Clique no link atualizar na faixa.
5. Aguarde até que o reinício do Microsoft Teams e, em seguida, repita a etapa 1 para ver se o aplicativo é atualizado.

Se você vir uma mensagem de falha ou se o número da versão for igual ao da etapa 4, o processo de atualização falhou.

## <a name="troubleshoot-installation-and-update-issues"></a>Solucionar problemas de instalação e atualização

### <a name="troubleshoot-installation-issues"></a>Solucionar problemas de instalação

Quando o Microsoft Teams é instalado, o instalador do teams registra a sequência de eventos em%LocalAppData%\SquirrelTemp\SquirrelSetup.log. A primeira coisa a procurar é uma mensagem de erro ou uma pilha de chamadas próxima ao final do log. Observe que as pilhas de chamadas no início do log podem não significar que há um problema de instalação. Pode ser mais fácil comparar seu log com o log a partir de uma instalação bem-sucedida (mesmo em outro computador) para ver o que é esperado.

Se SquirrelSetup. log não indicar a causa ou se precisar de mais informações para solucionar o problema, consulte [coletar e analisar logs de aplicativos e do sistema](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Solucionar problemas de atualização

Quando o Microsoft Teams é instalado com êxito, o local do log muda de%LocalAppData%\SquirrelTemp para%AppData%\Microsoft\Teams. Nesse local, há dois arquivos de log de interesse, SquirrelSetup. log e logs. txt.

- O arquivo SquirrelSetup. log nesse local é escrito por Update. exe, que é um executável que serve o aplicativo Teams.
- O arquivo log. txt é usado pelo aplicativo Teams (especificamente Teams. exe) para gravar eventos significativos do aplicativo. Ele provavelmente conterá informações de falha.

Esses arquivos de log contêm informações de identificação pessoal (PII) e, portanto, não são enviados à Microsoft.

O Microsoft Teams pode iniciar automaticamente o processo de atualização (dependendo da política) ou os usuários podem verificar manualmente se há atualizações acessando a imagem do perfil > verificar se há **atualizações**. Os dois métodos usam a seguinte sequência de eventos.

1. **Verifique se há atualizações**. O Teams faz uma solicitação da Web e inclui a versão atual do aplicativo e as informações do toque de implantação. O objetivo desta etapa é obter o link de download. Uma falha nesta etapa é registrada em logs. txt.
2. **Baixar atualização**. O Teams baixa a atualização usando o link download obtido da etapa 1. Quando o download estiver concluído, o Teams chama Update. exe para testar o download. Uma falha de download também é registrada em logs. txt.
3. **Testar a atualização**. O conteúdo baixado é verificado e desempacotado em uma pasta intermediária,%LocalAppData%\Microsoft\Teams\stage), que é feita por Update. exe. As falhas nesta etapa são registradas no SquirrelTemp. log.
4. **Instale a atualização**. Há várias maneiras de iniciar o Microsoft Teams. O sistema inicia automaticamente o Microsoft Teams quando um usuário faz logon ou você pode iniciar o Teams por meio de um atalho. Nesta etapa, Update. exe verifica a presença da pasta de preparação, verifica o conteúdo novamente e executa operações de arquivo para destestar o aplicativo. O backup da pasta de aplicativo antiga no%LocalAppData%\Microsoft\Teams\current é feito em%LocalAppData%\Microsoft\Teams\previous e a pasta do estágio é renomeada para "Current". As falhas nesta etapa são registradas no SquirrelTemp. log.

Se SquirrelTemp. log ou logs. txt não contiver informações suficientes para determinar a causa subjacente, e você precisar de mais informações para solucionar o problema, vá para [coletar e analisar logs do aplicativo e do sistema](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Coletar e analisar logs de aplicativos e do sistema

Esta seção descreve como coletar e analisar logs de aplicativo e sistema para obter informações mais abrangentes a fim de solucionar o problema. Você usará as ferramentas do Sysinternals para concluir essas etapas. Para saber mais, confira [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).

### <a name="collect-logs"></a>Coletar logs

1. Baixe as [ferramentas Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Extraia o arquivo zip para a pasta% TEMP% na unidade local.
3. Abra um prompt de comando elevado e siga este procedimento:

    1. Execute o seguinte para acessar sua pasta TEMP:

        ```
        cd /d %TEMP%
        ```
    2. Copie os logs de instalação e de aplicativo. Observe que, dependendo do ponto de falha, alguns desses registros podem não estar presentes.

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Execute o seguinte para capturar os identificadores abertos.

        ```
        handle > handles.txt
        ```

    4. Execute o seguinte para capturar as DLLs abertas.

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. Execute o seguinte para capturar os drivers que estão em execução.

        ```
        driverquery /v > driverquery.txt
        ```

    6. Execute o seguinte para capturar as listas de controle de acesso (ACLs) da pasta Teams.

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analisar logs (para usuários avançados)

Uma atualização com falha pode resultar em um comportamento imprevisível do aplicativo. Por exemplo, os usuários podem não conseguir sair do Microsoft Teams, ter uma versão obsoleta do teams ou não podem iniciar o Teams. Se você tiver um problema durante uma atualização, o primeiro lugar para procurar a causa é SquirrelTemp. log. Estes são os diferentes tipos de falhas de atualização, listadas da mais comum ao menos comum e como analisá-los e solucioná-los usando logs.

#### <a name="unable-to-exit-teams"></a>Não é possível sair do Microsoft Teams

Como o Teams determina que ele precisa se atualizar para uma versão mais recente, ele baixa e prepara o novo aplicativo e aguarda a oportunidade de reiniciar a si mesmo na próxima vez em que o computador estiver ocioso. Um problema comum durante esse processo é quando outro processo ou um driver de sistema de arquivos bloqueia o processo Teams. exe, que impede que o Teams. exe saia. Como resultado, o aplicativo Teams não pode ser substituído pelo aplicativo testado e recém-baixado.

Dicas para solução de problemas:

- Para confirmar que é o problema que você está experimentando, saia do Teams (clique com o botão direito do mouse em equipe na barra de tarefas e clique em **sair**). Em seguida, abra o Gerenciador de tarefas no Windows para ver se uma instância do teams ainda está em execução.  
- Se você não estiver no computador que está com esse problema, inspecione o SquirrelTemp. log coletado do computador que está apresentando esse problema e procure por uma entrada "programa: não é possível cancelar o processo no log".
- Para determinar o que está impedindo o Microsoft Teams. exe de sair, examine os logs DLLs. txt e manipula. txt. Esses são os processos que impedem a saída do teams.
- Outro culpado que pode impedir o Teams de sair é o driver do filtro do sistema de arquivos no modo kernel. Use a ferramenta SysInternals, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), para coletar o despejo do processo do modo kernel executando ```procdump -mk <pid>```, onde <pid> é a ID do processo obtida do Gerenciador de tarefas. Você também pode inspecionar o arquivo de log DRIVERQUERY. txt para ver os drivers de filtro ativos que podem interferir no Teams.
- Para recuperar esse Estado, reinicie o computador.

#### <a name="file-permissions"></a>Permissões de arquivo

O Teams cria várias subpastas e arquivos no perfil do usuário durante todo o processo de instalação e atualização. Como o aplicativo e o atualizador são executados como um usuário não elevado, as permissões de leitura e gravação devem ser concedidas nas seguintes pastas:

|La  |Usado por  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Instalador do Teams (por exemplo, Teams_Windows_x64. exe) durante a fase de instalação        |
|%LocalAppData%\Microsoft\Teams  | Teamr (Update. exe) do teams para extrair e testar o pacote do aplicativo durante o processo de atualização        |
|%AppData%\Microsoft\Teams   |  Aplicativo Teams (Teams. exe) para salvar as configurações, os Estados do aplicativo e o pacote de atualização baixado (pré-configurado)       |

Se o Microsoft Teams tiver acesso negado porque não pode gravar em um arquivo, outro aplicativo de software pode estar interferindo ou uma entrada de descritor de segurança pode estar limitando o acesso de gravação a uma pasta.

Dicas para solução de problemas:

- Procure provas de "acesso negado" em SquirrelTemp. log ou logs. txt. Verifique esses arquivos para ver se houve uma tentativa de gravar em um arquivo que falhou.
- Abra icacls. txt e procure a entrada de controle de acesso (ACE) efetiva que bloqueia as operações de gravação por um usuário que não seja um administrador. Geralmente, isso se encontra em uma das entradas DACL. Para obter mais informações, consulte a [documentação do icacls](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Arquivo corrompido

Em alguns casos, o software de criptografia pode alterar arquivos na pasta%LocalAppData%\Microsoft\Teams, o que pode impedir que as equipes comecem. Isso pode acontecer a qualquer momento, mesmo quando o aplicativo não estiver sendo atualizado. Infelizmente, quando um arquivo está corrompido, a única maneira de recuperar esse estado é desinstalar e reinstalar o Microsoft Teams.

> [!NOTE]
> Se você não conseguir determinar a causa do problema usando qualquer uma dessas etapas, talvez queira experimentar uma sessão do [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) . O Process Monitor é uma ferramenta Sysinternals que registra o acesso ao sistema de arquivos e ao registro.

## <a name="related-topics"></a>Tópicos relacionados

- [Obter clientes para o Teams](get-clients.md)
- [Atualizações de cliente do Teams](teams-client-update.md)