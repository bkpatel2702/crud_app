In This crud_app, I have added the new functionality for the adding image from the desktop.
First, we will install the ruby on rails in the system with its dependencies.

Then, we will follow the provided steps in the GitHub repository named https://github.com/spkdroid/CRUD-RubyOnRails#readme.

We will move on to creating the project. First, we will use the command “rails new crud_app” to make the folder and open it.

Now, it’s time to use a scaffold; it helps generate name and description strings to create some details.

Then, we will do the migration using the rails command “db:migrate” command.

After that, we will change the root with ‘tasks#index’ to set it for a homepage.

After that, we will create some data using 

“Task.create(name: "Task 1", description: "Description for Task 1")
Task.create(name: "Task 2", description: "Description for Task 2)”.

After that, we will copy some basic CSS code provided in the readme file and add something from outside.

Now, we will add the functionality to upload an image while creating the post and save the view when it’s created.

Before you start these steps, delete the old posts.

First, we will use the command: rails active_storage:install 

Now, use the “rails db:migrate” command to migrate all new changes.

Then, we move to the models/tasks.rb file and add “has_one_attached :image” before the end.

After that, go to the views/tasks/_form.html.erb file, add 
“</div class="field">
    <%= form.label :image %>
    <%= form.file_field :image %>
  <div>” before the form.submit.

Now, go to the controllers/tasks_controller.rb, go to the very end where the tasks_params is located, in the permit, add “, :image” to give the permissions for image.

After that, in the tasks/show.html.erb file, add “
<div>
  <%= image_tag(@task.image, style:'width:40%') %>
</div>” code. This will show the image when we create the new task, save that and try to retrieve it. 
    
Reference:
Deanin (2022) Active storage for image uploads | ruby on rails 5.2 tutorial, YouTube. Available at: https://www.youtube.com/watch?v=fVtGy3QL9xg. 
