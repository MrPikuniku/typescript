


Exercice 1


Questio 1


Que se passe-t-il ?

Il y a un message d'erreur: 
Type 'boolean' is not assignable to type 'string'.


Comment pouvez-vous typer a pour qu’elle accepte une chaîne de caractères ou un booléen ?
let a = string|boolean;

Questio 2

function isEven(n:number){
    if (n%2==0){
        return true ;

    }
    return false  
} 
jygjhghoiuyugkyiujlk glrkjirlkt
let isOdd = (n: number): boolean => {
    if(n%2!=0){
        return true;
    }
    return false ; 
    
}

Question 3

enum OrderStatusEnum  {
    Processing,  
    
    Shipped,
    
    Delivered = "delivered",
}

type OrderStatusLitteral = "processing" | "shipped" | "delivered";  

let statusEnum = OrderStatusEnum.Processing;

let deliveredEnum = OrderStatusEnum.Delivered;

let StatusLitteral: OrderStatusLitteral;
statusLitteral = "processing"; 



Question 4 

let numbersArray: number[];

let numbersOrStringArray: number|string[];

let userTupple: [string,string,number] = ["SANGARE", "Maxime",15 ];



Exercice 2

Question 1

type User = {
    mail:string;
    password:string;
    birthDate: Date|null;
};

type RegisteredUser = User & {
    id: number;

    registeredAt: Date;

};

let person: User = {
mail: "sangaremoon@gmail.com",password: "uhfdiuehf"
}; 

let inscrit: RegisteredUser = {id: 500, registeredAt: new Date(5),mail:"reijooipejrogire",password:"rgiolrtdsdgfiiogioeiordod" }; 

Question 2

interface Animals{
    name: string;
}
A faire 

A faire

Question 3

A vérifier//
type Todo = Partial<{
    id: number;
    createdAt: Date;
    title: string;
    completed: boolean;
    dueDate?: Date;
    metadata?:{[key:string]: string|number|boolean } ;    

}>

const todo: Todo = {
    title: "Finir le TP",
    completed: false,
    metadata: {
	  difficulty: 100,
	  author: "Sasha Touille"  
	}
}

type CreationTodoData = Omit<Omit<Todo,"id">,"createdAt">   
   
const creationData: CreationTodoData = {
	title: "Ma tâche",
    completed: false,
    dueDate: new Date(),
}

Type utilitaire séléctionnant  certaines  propriétés : Pick 

type MutationTodoData = Partial<Omit<Todo,"createdAt">>;  

const mutationData: MutationTodoData = {
	id: 23,
    completed: true,
}

On utilise Required pour rendre toutes les propriétés requises 



Question 4

interface ApiResponse  {
    success: boolean;
}

interface  ApiSuccessResponse extends ApiResponse{
    succes: true;
    body: object;
}

interface ApiErrorResponse extends ApiResponse{
    success: false;
    error: string;
}
                                        
function callApi(){
    let error = Math.round(Math.random() * 10) % 2 === 0;
    if(error){
        return Promise.resolve({ success: false,  error: "Mon erreur",body:null });
    }

    return Promise.resolve({success: true, body:{title: "Mon titre"}, error: null}); 
}


callApi().then((value) =>  console.log(value.success ? value.body : value.error))

Exercice 3 

Question 1

document.addEventListener('DOMContentLoaded', () => {
  const formulaire = document.querySelector<HTMLFormElement>('.my-form');
  if (formulaire) {
    console.log('Form found:', formulaire);
  } else {
    console.error('Form not found!');
  }

  const entrees = document.querySelectorAll<HTMLInputElement | HTMLTextAreaElement | HTMLSelectElement>('.my-inputs');
  if (entrees.length > 0) {
    entrees.forEach(input => {
      console.log('entrées trouvées:', input);
    });
  } else {
    console.error('pas d'entrée trouvée!');
  }
});

Question 2




Question 3



