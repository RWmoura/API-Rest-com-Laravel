Aluno: Rafael Ribeiro Moura
instituição: Unifil
Curso: Ciência da Computação

Sistema de Gerenciamento de Tarefas (API)

API criada em PHP com Laravel.

A API é capaz de lidar com as seguintes operações:

→ Listar todas as tarefas
→ Obter detalhes de uma tarefa específica
→ Criar uma nova tarefa
→ Atualizar os dados de uma tarefa existente
→ Excluir uma tarefa

Cada task possui: 
→ Título (obrigatório)
→ Descrição (obrigatório)
→ Status (concluída ou não concluída)

Teste da API realizado com o Postman.



Rotas criadas: 
→ Route::get('/tasks', [TaskController::class, 'index']);
→ Route::post('/tasks', [TaskController::class, 'store']);
→ Route::get('/tasks/{task}', [TaskController::class, 'show']);
→ Route::put('/tasks/{task}', [TaskController::class, 'update']);
→ Route::delete('/tasks/{task}', [TaskController::class, 'destroy']);

http://localhost:8000/api/tasks

Key's(Parâmetros )necessários: 
→ title         #Título da tarefa em si
→ description   #Descrição da tarefa em si
→ status        #Status da tarefa(Completa ou incompleta)

Respostas(Testes):

(POST)
http://localhost:8000/api/tasks?title=Criar API&description=Criando uma API Rest com laravel em php para gerenciar tarefas&status=Completa

    {
        "id": 1,
        "title": "Criar API",
        "description": "Criando uma API Rest com laravel em php para gerenciar tarefas",
        "status": "Completa",
        "created_at": "2023-07-12T14:53:23.000000Z",
        "updated_at": "2023-07-12T14:53:23.000000Z"
    }

(POST)
http://localhost:8000/api/tasks?title=Testar API&description=Testar API criada&status=Incompleta

    {
        "id": 2,
        "title": "Testar API",
        "description": "Testar API criada",
        "status": "Incompleta",
        "created_at": "2023-07-12T14:54:12.000000Z",
        "updated_at": "2023-07-12T14:54:12.000000Z"
    }

(POST)
http://localhost:8000/api/tasks?title=Documentar API&description=Criando uma documentação para a API Rest com laravel em php&status=Completa

{
    "title": "Documentar API",
    "description": "Criando uma documentação para a API Rest com laravel em php",
    "status": "Completa",
    "updated_at": "2023-07-12T18:31:18.000000Z",
    "created_at": "2023-07-12T18:31:18.000000Z",
    "id": 4
}

(DELETE)
http://localhost:8000/api/tasks/4

[]

(GET)
http://localhost:8000/api/tasks

[
    {
        "id": 1,
        "title": "Criar API",
        "description": "Criando uma API Rest com laravel em php para gerenciar tarefas",
        "status": "Completa",
        "created_at": "2023-07-12T14:53:23.000000Z",
        "updated_at": "2023-07-12T14:53:23.000000Z"
    },
    {
        "id": 2,
        "title": "Testar API",
        "description": "Testar API criada",
        "status": "Incompleta",
        "created_at": "2023-07-12T14:54:12.000000Z",
        "updated_at": "2023-07-12T14:54:12.000000Z"
    }
]

 