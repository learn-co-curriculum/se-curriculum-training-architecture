# Curriculum Architecture Overview

## Introduction

Curriculum for the Software Engineering program relies heavily on two platforms:

- **Canvas**: a learning management system (LMS) designed for a broad range of
  functionality, including course organization, grading, roster management, etc.
  The primary entry point for students as they navigate the curriculum.
- **GitHub**: a cloud-based platform for hosting Git repositories. Where our
  lessons live, and where students go to download and work on code we provide.

Broadly speaking, the curriculum team uses Canvas to **structure and sequence**
the curriculum, and uses GitHub to **write and maintain** individual lessons.

For every lesson in Canvas, there is a corresponding repository on GitHub.
Whenever we need to create a lesson, we create a repository on GitHub and use
tooling to push the lesson to Canvas. Whenever we need to update a lesson, we
update it on GitHub and use tooling to push those updates to Canvas.

## GitHub to Canvas

The tool that we use to push changes from GitHub to Canvas is the
[github-to-canvas][] Ruby gem.

The github-to-canvas gem works by:

- Converting the README.md file from a lesson to HTML, including some additional
  markup that allows students to fork the lesson
- Using the [Canvas API][canvas api] to update/create a lesson using that HTML

In the coming lessons, we'll use the github-to-canvas gem to create and update
lessons. So now's a good time to get it set up! Follow the installation and
setup instructions:

- [github-to-canvas setup][github-to-canvas]

During the setup, you'll need to configure a couple secret environment variables
so that the gem can interact with the Canvas API. Reach out to the curriculum
team and they'll provide you with the info you need.

Verify that you've installed the gem:

```console
$ github-to-canvas --help
```

Now that you've got the gem set up, it's time to create your first lesson!

[github-to-canvas]: https://github.com/learn-co-curriculum/github-to-canvas
[canvas api]: https://canvas.instructure.com/doc/api/index.html
