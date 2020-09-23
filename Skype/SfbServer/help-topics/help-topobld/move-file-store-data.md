---
title: Mover dados do repositório de arquivos para um novo repositório de arquivos no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Se você precisar remover o servidor de arquivos que está atuando atualmente como o repositório de arquivos para sua implantação do Skype for Business Server 2015, ou se precisar fazer outras alterações que tornaram o repositório de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento. Em seguida, você precisará executar as seguintes etapas:'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215582"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Mover dados do repositório de arquivos para um novo repositório de arquivos no Skype for Business Server 2015

Se você precisar remover o servidor de arquivos que está atuando atualmente como o repositório de arquivos para sua implantação do Skype for Business Server 2015, ou se precisar fazer outras alterações que tornaram o repositório de arquivos atual indisponível, primeiro será necessário criar um novo compartilhamento. Em seguida, você precisará executar as seguintes etapas:

1. Encerre os serviços do Skype for Business Server 2015 que usam o repositório de arquivos que você planeja remover.

2. Defina o repositório de arquivos no construtor de topologia e publique as alterações para disponibilizar o novo repositório de arquivos para sua implantação.

3. Mova os dados para o novo repositório de arquivos.

4. Reinicie os servidores ou serviços.

5. Opcionalmente, remova o compartilhamento de arquivo e a pasta de arquivo antigos.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover os dados do repositório de arquivos de um repositório para o novo

1. Faça logon em um computador como membro do grupo grupo rtcuniversersalserveradmins ou CsServerAdministrator onde o Skype for Business Server 2015, as ferramentas administrativas estão instaladas.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.

4. Para cada pool de diretores, diretor, servidor Standard Edition e pool de front-ends que usa o repositório de arquivos que você planeja remover, selecione o servidor ou pool, clique em **ação**e em **parar todos os serviços**.

5. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

6. Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.

7. Selecione um servidor ou pool que usa o repositório de arquivos e faça o seguinte:

8. Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades**.

9. Em **Editar propriedades**, em **associações**, em **repositório de arquivos**, clique em **novo**.

10. Em **definir novo repositório de arquivos**, em **FQDN do servidor de arquivos**, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos. Em **compartilhamento de arquivos**, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK**.

     > [!IMPORTANT]
     > Esta etapa define um novo repositório de arquivos para uso no construtor de topologias. Você pode defini-la somente uma vez, e não para cada servidor. Antes de publicar a topologia, você deve criar o compartilhamento de arquivos definido no servidor de arquivos especificado. Para detalhes, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Para cada servidor ou pool que usa o repositório de arquivos, faça o seguinte:

12. Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades**.

13. Em **Editar propriedades**, em **associações**, em **repositório de arquivos**, selecione o novo compartilhamento de arquivos e clique em **OK**.

14. Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Skype for Business Server, conforme necessário. Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Inicie um prompt de comando: clique em **Iniciar**, clique em **executar**e digite cmd.exe.

16. Na linha de comando, digite o seguinte:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > A opção/S copia sobre arquivos, diretórios e subdiretórios. A opção/XF ignora qualquer arquivo chamado Meeting. Active. Versões atuais do robocopy.exe com a opção /MT aumentam muito a velocidade da cópia usando vários threads. Para a opção/LOG, use um caminho de diretório e um nome de arquivo de log na forma de C:\Logfiles\log.txt. Essa opção cria um arquivo de log de operações no local nomeado.

17. Quando a cópia de dados estiver concluída, no painel de controle do Lync Server, clique em **topologia**e em **status**.

18. Para cada servidor ou pool em que você interrompeu serviços, selecione o servidor ou pool, clique em **ação**e em **Iniciar todos os serviços**.

19. Remova o repositório de arquivos antigo da topologia e publique-a. Para detalhes, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Opcional) Faça logon no computador que contém o repositório de arquivos que foi removido como membro do grupo Administradores local ou grupo Admins. de Domínio e remova o compartilhamento de arquivos e o diretório antigos.

## <a name="see-also"></a>Confira também

[Reatribuir um servidor para um repositório de arquivo diferente](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Remover um repositório de arquivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
