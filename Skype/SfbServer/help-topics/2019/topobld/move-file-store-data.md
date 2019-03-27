---
title: Dados do repositório de arquivos de movimentação para um novo repositório de arquivos no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Se você precisa remover o servidor de arquivos que esteja atuando como o repositório de arquivos para seu Skype para implantação de servidor de negócios ou se você precisar fazer outras alterações que tornaria o arquivo atual armazenam indisponível, você precisará criar um novo compartilhamento. Em seguida deverá executar as seguintes etapas:'
ms.openlocfilehash: 0f9552e9de66924524ef2ac5c66d125689061b88
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890385"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Dados do repositório de arquivos de movimentação para um novo repositório de arquivos no Skype para Business Server

Se você precisa remover o servidor de arquivos que esteja atuando como o repositório de arquivos para seu Skype para implantação de servidor de negócios ou se você precisar fazer outras alterações que tornaria o arquivo atual armazenam indisponível, você precisará criar um novo compartilhamento. Em seguida deverá executar as seguintes etapas:

1. Desligue o Skype para serviços de Business Server que usam o repositório de arquivos que você planeja remover.

2. Definir o repositório de arquivos no construtor de topologia e publicar as alterações para disponibilizar o novo arquivo de repositório para sua implantação.

3. Mova os dados para o novo repositório de arquivos.

4. Reinicie os servidores ou os serviços.

5. Opcionalmente, remova o compartilhamento de arquivos ou a pasta de arquivos antiga.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover os dados do repositório de arquivos de um repositório para outro

1. Faça logon em um computador como membro do grupo RTCUniversersalServerAdmins ou CsServerAdministrator onde o Skype para Business Server, ferramentas administrativas estão instaladas.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 

4. Para cada pool de diretores, diretor, servidor Standard Edition e pool de Front-End que usa o repositório de arquivos que você planeja remover, selecione o servidor ou pool, clique em **ação**e, em seguida, clique em **Parar todos os serviços**.

5. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

6. Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique **Skype para o construtor de topologia de servidor de negócios**.

7. Selecione um servidor ou pool que usa o repositório de arquivos e faça o seguinte:

8. Clique com o botão direito do mouse no servidor ou no pool e em **Editar Propriedades**. 

9. Em **Editar propriedades**, **Associações**, **Repositório de arquivos**, clique em **Novo**.

10. Em **Definir Novo Repositório de Arquivos**, em **FQDN do servidor de arquivo**, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos. Em **Compartilhamento de arquivos**, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK**.

     > [!IMPORTANT]
     > Essa etapa define um novo repositório de arquivos para uso no construtor de topologia. Você o define apenas uma vez, não para cada servidor. Antes de você publicar a topologia, deverá criar o compartilhamento de arquivos definido no servidor de arquivos definido. Para obter detalhes, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Para cada servidor ou pool que usa o repositório de arquivos, faça o seguinte:

12. Clique com o botão direito do mouse no servidor ou no pool e em **Editar Propriedades**.

13. Em **Editar Propriedades**, **Associações**, **Repositório de arquivos**, selecione o novo compartilhamento de arquivos e em **OK**.

14. Publique a topologia, verifique o status de replicação e execute o Skype para o Assistente de implantação de servidor de negócios conforme necessário. Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Inicie um prompt de comando: clique em **Iniciar**, clique em **Executar**e digite cmd.exe.

16. Na linha de comando, digite o seguinte:

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > A opção /S copia sobre os arquivos, diretórios e subdiretórios. A opção /XF ignora os arquivos nomeados como Meeting.Active. As versões atuais de robocopy.exe com a opção /MT aumentam significativamente a velocidade da cópia usando vários threads. Para o switch /LOG, use um diretório caminho e o log de nome de arquivo no formato de C:\Logfiles\log.txt. Essa opção cria um arquivo de log das operações no local nomeado.

17. Quando a cópia de dados estiver concluída, no painel de controle do Lync Server, clique em **topologia**e, em seguida, clique em **Status**.

18. Para cada servidor ou pool cujos serviços você interrompeu, selecione o servidor ou pool, clique em **Ação** e em **Iniciar todos os serviços**.         

19. Remova o antigo repositório de arquivos da topologia e publique a topologia. Para obter detalhes, veja [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Opcional) Faça logon no computador que contém o repositório de arquivos que você acabou de remover como membro do grupo local de administradores ou do grupo de administradores de domínio e remova o antigo diretório e compartilhamento de arquivos.

## <a name="see-also"></a>Consulte Também

[Reatribuir um servidor para um repositório de arquivo diferente](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Remover um repositório de arquivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
